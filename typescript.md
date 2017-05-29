# TypeScript

## Instalation

`npm install -g typescript@beta` for V2 [beta](https://blogs.msdn.microsoft.com/typescript/2016/07/11/announcing-typescript-2-0-beta)

Nice [introduction](https://toddmotto.com/typescript-the-missing-introduction)

[www.typescriptlang.org](http://www.typescriptlang.org/)

A [JavaScript](./javascript) pre-compiler from Microsoft, excellent [Channel 9](https://channel9.msdn.com/posts/Anders-Hejlsberg-Introducing-TypeScript) video from Anders Hejlsberg.

Some `TypeScript` with some embedded `JSX`.

```typescript
class MyComponent extends React.Component {
  handleClick = (e) => {
    this.setState({clicked: true});
  }
  render() {
    return <a href="#" onClick={this.handleClick}>Click me</a>;
  }
}

```
The `<a href="#" onClick={this.handleClick}>Click me</a>;` is JSX, which I shall have to learn.

[Deep dive](https://www.gitbook.com/book/basarat/typescript/details)

 * Sitecore [Training](https://www.sitepoint.com/premium/courses/introducing-typescript-2933/?utm_source=sitepoint&utm_medium=email&utm_campaign=typescript-launch)
 
_c.f._

 * [React](./react.md)
 * [JSX](./jsx.md)
 * [Angular](./angular.md)