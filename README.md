## Description of the Vue.js Component

**Component:** `inputTag`

This component allows users to input and manage a set of tags. The main features and functionalities include:

### 1. Tag Input:
- Users can type a tag into an input field and add it to the list by pressing the Enter key.
- If a user tries to add a tag that already exists in the list, it won't be duplicated.
- If the input field is empty and the user presses the Backspace key, the last tag in the list will be removed.

### 2. Tag Display:
- Entered tags are displayed in a horizontal list.
- Each tag comes with an "X" button that allows for its removal from the list.

### 3. Styling and Design:
- The component has an inline-flex design with a border and a white background.
- Tags are displayed with a gray border, and hovering over the "X" button changes its background to a light gray.

### 4. Events and Properties:
- The component has an `onTagsChange` property used to notify parent components about changes in the tag list.
- Every time a tag is added or removed, the `onTagsChange` method is invoked with the updated list of tags.

---

This component is ideal for situations where users need to input a series of keywords, categories, or any other type of tags. For instance, it could be useful in a content management system, a task application, among others.