# nativebase.io-style-cheatsheet
Here’s a **complete** NativeBase cheatsheet covering all major properties for styling components:

---

### **1. Colors**
- **`bg` / `backgroundColor`**: Set background color
  ```jsx
  <Box bg="blue.500" />
  <Box backgroundColor="#FF5733" />
  ```

- **`color`**: Set text color
  ```jsx
  <Text color="red.500" />
  ```

- **`opacity`**: Set element opacity
  ```jsx
  <Box opacity={0.8} />
  ```

---

### **2. Borders**
- **`border`**: Set border on all sides
  ```jsx
  <Box border={1} borderColor="gray.200" />
  ```

- **`borderColor`**: Set border color
  ```jsx
  <Box borderColor="blue.300" />
  ```

- **`borderRadius` / `rounded`**: Set border radius for rounded corners
  ```jsx
  <Box borderRadius="lg" />
  <Box rounded="md" />
  ```

- **`borderWidth`**: Set border thickness
  ```jsx
  <Box borderWidth={2} />
  ```

- **`borderTopWidth`, `borderBottomWidth`, `borderLeftWidth`, `borderRightWidth`**: Individual borders
  ```jsx
  <Box borderTopWidth={1} />
  ```

---

### **3. Shadows**
- **`shadow`**: Apply shadow using predefined levels
  ```jsx
  <Box shadow={4} />
  ```

- **`shadowColor`**: Custom shadow color
  ```jsx
  <Box shadowColor="rgba(0, 0, 0, 0.3)" />
  ```

---

### **4. Layout - Flexbox**
- **`display`**: Set layout type (`flex`, `block`, etc.)
  ```jsx
  <Box display="flex" />
  ```

- **`flexDirection`**: Set flexbox direction (`row`, `column`)
  ```jsx
  <Box flexDirection="row" />
  ```

- **`justifyContent`**: Distribute space along main axis (`center`, `space-between`)
  ```jsx
  <Box justifyContent="center" />
  ```

- **`alignItems`**: Align children along cross axis (`center`, `flex-start`)
  ```jsx
  <Box alignItems="flex-start" />
  ```

- **`flexWrap`**: Control wrapping of children (`wrap`, `nowrap`)
  ```jsx
  <Box flexWrap="wrap" />
  ```

- **`flex`**: Grow, shrink, or specify flex-basis
  ```jsx
  <Box flex={1} />
  ```

- **`alignSelf`**: Override `alignItems` for individual child
  ```jsx
  <Box alignSelf="flex-end" />
  ```

---

### **5. Margin & Padding**
- **`m` / `margin`**: Margin on all sides
  ```jsx
  <Box m={4} />
  ```

- **`p` / `padding`**: Padding on all sides
  ```jsx
  <Box p={4} />
  ```

- **Horizontal & Vertical:**
  - **`mx` / `my`**: Margin X or Y axis
    ```jsx
    <Box mx={2} my={4} />
    ```
  - **`px` / `py`**: Padding X or Y axis
    ```jsx
    <Box px={4} py={2} />
    ```

- **Individual sides:**
  - **`mt`, `mb`, `ml`, `mr`**: Margin (top, bottom, left, right)
    ```jsx
    <Box mt={2} mb={4} />
    ```
  - **`pt`, `pb`, `pl`, `pr`**: Padding (top, bottom, left, right)
    ```jsx
    <Box pt={4} pl={2} />
    ```

---

### **6. Positioning**
- **`position`**: Set `relative`, `absolute`, or `fixed`
  ```jsx
  <Box position="absolute" top={0} />
  ```

- **`top`, `right`, `bottom`, `left`**: Position offsets
  ```jsx
  <Box top={4} right={0} />
  ```

- **`zIndex`**: Stacking order
  ```jsx
  <Box zIndex={1} />
  ```

---

### **7. Size**
- **`w` / `width`**: Set width
  ```jsx
  <Box w="100%" />
  ```

- **`h` / `height`**: Set height
  ```jsx
  <Box h="50px" />
  ```

- **`size`**: Shortcut for both width and height
  ```jsx
  <Box size="100px" />
  ```

- **`minW`, `maxW`, `minH`, `maxH`**: Set min/max dimensions
  ```jsx
  <Box minW="100px" maxW="500px" />
  ```

---

### **8. Typography**
- **`fontSize`**: Text size
  ```jsx
  <Text fontSize="lg" />
  ```

- **`fontWeight`**: Text weight (boldness)
  ```jsx
  <Text fontWeight="bold" />
  ```

- **`textAlign`**: Text alignment (`center`, `left`, `right`)
  ```jsx
  <Text textAlign="center" />
  ```

- **`lineHeight`**: Space between lines of text
  ```jsx
  <Text lineHeight="short" />
  ```

---

### **9. Responsive Design**
NativeBase supports responsive values using arrays or objects:
- **Arrays**: Different values for breakpoints
  ```jsx
  <Box w={['100%', '75%', '50%']} />
  ```

- **Objects**: `base`, `sm`, `md`, `lg` breakpoints
  ```jsx
  <Box p={{ base: 2, md: 4, lg: 6 }} />
  ```

---

### **10. Other Utility Properties**
- **`cursor`**: Control mouse cursor
  ```jsx
  <Box cursor="pointer" />
  ```

- **`overflow`**: Control content overflow (`hidden`, `scroll`)
  ```jsx
  <Box overflow="hidden" />
  ```

- **`elevation`**: Control shadow for Android
  ```jsx
  <Box elevation={4} />
  ```

- **`textOverflow`**: Handle text overflow (ellipsis)
  ```jsx
  <Text isTruncated />
  ```

- **`transition`**: Control transitions for animations
  ```jsx
  <Box transition="all 0.3s ease" />
  ```

- **`boxShadow`**: Set custom shadow (similar to `shadow` but allows for CSS-like values)
  ```jsx
  <Box boxShadow="0px 4px 6px rgba(0, 0, 0, 0.1)" />
  ```

---

### **11. Pseudo Props**
NativeBase supports pseudo props for handling interactive states like hover, focus, etc.

- **`_hover`**: Apply styles on hover
  ```jsx
  <Box _hover={{ bg: "blue.600" }} />
  ```

- **`_focus`**: Apply styles on focus
  ```jsx
  <Input _focus={{ borderColor: "blue.500" }} />
  ```

- **`_pressed`**: Styles when pressed (for touchable elements)
  ```jsx
  <Button _pressed={{ bg: "blue.700" }} />
  ```

---

### **12. Space & Gap**
- **`space`**: Set space between children for flex/grid layouts
  ```jsx
  <VStack space={4}>
    <Box />
    <Box />
  </VStack>
  ```

- **`gap`**: Set gap between children (CSS Grid and flexbox support)
  ```jsx
  <Box gap={4}>
    <Box />
    <Box />
  </Box>
  ```

---

### **13. Custom Theming**
NativeBase allows you to customize its theme via the `extendTheme` function:
```jsx
const customTheme = extendTheme({
  colors: {
    primary: {
      500: "#6200EE",
    },
  },
  fontConfig: {
    Roboto: {
      400: {
        normal: "Roboto-Regular",
      },
    },
  },
  fonts: {
    heading: "Roboto",
    body: "Roboto",
  },
});
```

You can then pass the theme to the `NativeBaseProvider`:
```jsx
<NativeBaseProvider theme={customTheme}>
  <App />
</NativeBaseProvider>
```

---

This comprehensive cheatsheet should help you with all essential NativeBase styling properties and utilities!
