---
title: Memento Design Pattern
---

## The problem

Implementation of _Undo_ mechanism in the application (e.g. text editor).

## The implementation

```ts
/**
 * The Memento. A state of the object at one point of time
 */
class EditorState {
  private readonly _content: string;
  public get content(): string {
    return this._content;
  }

  constructor(content: string) {
    this._content = content;
  }
}
```

```ts
/**
 * The Caretaker. Maintains the history of the editor
 */
class EditorHistory {
  private _editorStates: EditorState[] = [];

  public push(state: EditorState) {
    console.log(this._editorStates);
    this._editorStates.push(state);
  }

  public pop(): EditorState | undefined {
    return this._editorStates.pop();
  }
}
```

```ts
/**
 * The Originator
 * Handles the Editor _window_ (textarea) and provides its own state
 */
class Editor {
  private _content: string;

  public get content(): string {
    return this._content;
  }

  public set content(value: string) {
    this._content = value;
  }

  public createState(): EditorState {
    return new EditorState(this._content);
  }

  public restoreState(state?: EditorState): void {
    if (state) {
      this.content = state.content;
    }
  }
}
```

```ts
/**
 * index.ts
 * This could be something named _EditorManager_
 */
const editor = new Editor();
const editorHistory = new EditorHistory();

editor.content = "A";
editorHistory.push(editor.createState());

editor.content = "B";
editorHistory.push(editor.createState());

editor.content = "C";
editor.restoreState(editorHistory.pop());
console.log(editor.content); // "B"

editor.restoreState(editorHistory.pop());
console.log(editor.content); // "A"
```
