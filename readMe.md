# Connection Dialogs Project

This project contains a React Native TypeScript application with two connection dialogs. The dialogs are shown based on the state of the application. Dialog 1 has 2 buttons and a FlatList, while Dialog 2 has 1 button and an Activity Indicator. The project follows a modular structure to organize the components, subcomponents, and custom hooks.

## Folder Structure
```tsx
src/
  ├─ components/
  │   ├─ ConnectionDialogs/
  │   │   ├─ index.tsx
  │   │   ├─ styles.ts
  │   │   ├─ hooks/
  │   │   │   ├─ useFirstCustomHook.ts
  │   │   │   ├─ useSecondCustomHook.ts
  │   │   │   └─ ...
  │   │   ├─ subcomponents/
  │   │   │   ├─ CustomButton.tsx
  │   │   │   ├─ FlatListComponent.tsx
  │   │   │   ├─ Dialog1.tsx
  │   │   │   ├─ Dialog2.tsx
  │   │   │   └─ ...
  │   │   └─ types/
  │   │       └─ connectionDialogTypes.ts
  │   └─ ...
  └─ ...
```

## Example Usage

### ConnectionDialogs/index.tsx

```tsx
import React, { useState } from 'react';
import { View } from 'react-native';
import Dialog1 from './subcomponents/Dialog1';
import Dialog2 from './subcomponents/Dialog2';

const ConnectionDialogs = () => {
  const [dialogState, setDialogState] = useState(1);

  return (
    <View>
      {dialogState === 1 && <Dialog1 />}
      {dialogState === 2 && <Dialog2 />}
    </View>
  );
};

export default ConnectionDialogs;
```
### ConnectionDialogs/subcomponents/Dialog1.tsx
```tsx
import React from 'react';
import { View } from 'react-native';
import CustomButton from './CustomButton';
import FlatListComponent from './FlatListComponent';

const Dialog1 = () => {
  // Your component logic and hooks here

  return (
    <View>
      <FlatListComponent data={data} />
      <CustomButton title="Button 1" onPress={handleButton1Press} />
      <CustomButton title="Button 2" onPress={handleButton2Press} />
    </View>
  );
};

export default Dialog1;
```
### ConnectionDialogs/subcomponents/Dialog2.tsx
```tsx
import React from 'react';
import { View, ActivityIndicator } from 'react-native';
import CustomButton from './CustomButton';

const Dialog2 = () => {
  // Your component logic and hooks here

  return (
    <View>
      <ActivityIndicator size="large" color="#0000ff" />
      <CustomButton title="Button 3" onPress={handleButton3Press} />
    </View>
  );
};

export default Dialog2;
```
This structure maintains a clear separation of concerns between the dialogs, while also organizing the subcomponents and hooks in a clean manner. You can conditionally render each dialog based on the `dialogState` value in the parent `ConnectionDialogs` component.
