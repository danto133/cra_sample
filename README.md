# Welcome to LYFE MERCHANT. We will go to Hell together. Let mentally prepared

## About Project

In this project, we will build components, create pages and implement logic with it.

## Repository

<https://bitbucket.org/binhnguyenthien/3forcom-lyfe-merchant-fo-2020/src/develop/>

## Design Workspace

<https://www.figma.com/file/sJB8sfuuvWESXuMCunOrHo/LYFE-App>

## Languages and Frameworks

- CRA
- TypeScript v3.9
- SCSS (node-sass) v4
- React v16.11
- Babel v8
- Hygen
- Jest v25 + Enzyme
- Storybook v5
- ESLint v6 + typescript-eslint v3.7
- Stylelint v13.6
- Prettier
- React-router-dom v5
- ...

## Files/Directories

| Path                    | Purpose                                                     |
| ----------------------- | ----------------------------------------------------------- |
| /.storybook/            | contains Storybook config files                             |
| /.editorconfig          | settings for `Editorconfig`                                 |
| /.eslintrc.js           | settings for `ESLint`                                       |
| /.hygen.js              | settings for `Hygen`                                        |
| /\_templates/           | contains scaffolding templates based on `Hygen`             |
| /.prettierrc.js         | settings for `Prettier`                                     |
| /.stylelintrc.js        | settings for `Stylelint`                                    |
| /.vscode/               | settings for `Visual Studio Code` workspace                 |
| /jest                   | settings for `Jest` and `Storybook`                         |
| /jest.config.`*`.js     | settings for `Jest` about behaviors                         |
| /package.json           | manifest file for Node.js projects                          |
| /tsconfig.json          | settings for `TypeScript`                                   |
| /tsconfig.test.json     | settings for `TypeScript` of `Test`                         |
| /dist/                  | contains production build codes                             |
| /src/components/        | contains Atomic Design components                           |
| /src/pages/             | contains pages                                              |
| /src/assets/            | contains images, movies, fonts                              |
| /src/lib/               | contains shared libraries                                   |
| /src/store/             | contains shared store                                       |
| /src/store/reducer      | contains shared store reducers                              |
| /src/store/sagas        | contains shared store sagas                                 |
| /src/store/types        | contains shared store types                                 |
| /src/index.tsx/         | contains root file                                          |
| /src/pages/app.tsx      | contains application page index                             |
| /src/`**`/routes.tsx    | contains application page routes                            |
| /src/main.scss          | contains shared styles                                      |
| /src/react-app-env.d.ts | contains shared types                                       |
---

## Command Line

| Path                    | Purpose                                                     |
| ----------------------- | ----------------------------------------------------------- |
| yarn start              | start the project                                           |
| yarn buid               | build the project                                           |
| gen:component:atom      | generate new `atomic` component                             |
| gen:component:molecule  | generate new `molecule` component                           |
| gen:component:organism  | generate new `organism` component                           |
| gen:component:page      | generate new `page` component                               |
| gen:component:template  | generate new `template` component                           |
| gen:component:util      | generate new `util` component                               |
| yarn storybook          | run the storybook                                           |
| yarn lint:script        | run `Eslint` to check the syntax                            |
| yarn lint:style         | run `Stylelint` to check the syntax                         |
| yarn lint               | run linter to check the syntax of both `Eslint & Stylelint` |
| yarn lint:script        | auto-fixes for the syntax of `Eslint`                       |
| yarn lint:script        | auto-fixes for the syntax of `Stylelint`                    |
| yarn format             | auto-fixes for the syntax of both `Eslint & Stylelint`      |
| yarn lint:typecheck     | check the syntax of `Typescript`                            |
| yarn test:unit          | run unit test                                               |
| yarn test:unit:watch    | run the unit test and watch it                              |
| yarn test:unit-update   | run unit test updates                                       |
| yarn test:page          | run page test                                               |
| yarn test:page:watch    | run the page test and watch it                              |
| yarn test:page-update   | run page test updates                                       |
---

### `Abem`

<https://css-tricks.com/abem-useful-adaptation-bem/>

**Note: Use only the `lowercase` format for `className`.**

```tsx
  //GOOD 🏆🏆🏆
  export const Sample:React.FC = props => (
    <div className="a-sample">{props.children}</div>
  );


  //NOT GOOD 💩💩💩
  export const Sample:React.FC = props => (
    <div className="a-Sample">{props.children}</div>
  );
```

**Note: Use only the `Single_Underscore(_) && Single-Dash(-)` format for `className`.**

```tsx
  //GOOD 🏆🏆🏆
  export const Sample = () => (
    <div className="a-sample">
      <span className="a-sample_title">Title</span>
    </div>
  );


  //NOT GOOD 💩💩💩
  export const Sample = () => (
    <div className="a--sample">
      <span className="a--sample__title">Title</span>
    </div>
  );
```

**Note: The `className` must be formatted as `block_element-modifier`. But `Sometimes` it will be formatted as `block_element_element-modifier`.**

```tsx
  //GOOD 🏆🏆🏆
  export const Sample = () => (
    <div className="a-sample">
      <span className="a-sample_element">One Element</span>
    </div>
  );

  export const Sample = () => (
    <div className="a-sample">
      <span className="a-sample_element1_element2">Two elements</span>
    </div>
  );


  //NOT GOOD 💩💩💩
  export const Sample = () => (
    <div className="a-sample">
      <span className="a-sample_element1_element2_element3">Greater than 2 elements</span>
    </div>
  );
```

### `Atomic`

<https://bradfrost.com/blog/post/atomic-web-design/>

### `Components`

- Use only `React-Hook`
- Follow the `rules of hook` (<https://reactjs.org/docs/hooks-rules.html>)

**Note: Use `mapModifiers` to generate `modifiers`.**

```tsx
  export const Component: React.FC<Props> = props => (
    <div className={mapModifiers('a-sample', props.modifiers)}>{props.children}</div>
  );
```

**Note: Use `// eslint-disable-next-line react-hooks/exhaustive-deps` when you want to avoid checking of the `useEffect` syntax (also on `useMemo & useCallback`)**

```tsx
  useEffect(() => {
    Todo Something...
  // eslint-disable-next-line react-hooks/exhaustive-deps
  }, []);
```

**Note: Use simple syntax when the component has no properties.**

```tsx
  //GOOD 🏆🏆🏆
  export const Component = () => (
    <div>Without children...</div>
  );

  export const Component: React.FC = props => (
    <div>{props.children}</div>
  );


  //NOT GOOD 💩💩💩
  export const Component: React.FC = props => (
    <div>Without children...</div>
  );
```

**Note: Clearly define the data type of the property.**

```tsx
  //GOOD 🏆🏆🏆
  interface Props {
    title: string;
  }

  //NOT GOOD 💩💩💩
  interface Props {
    title: any;
  }
```

**Note: Please leave TODO when you encounter some unresolved issues immediately.**

```tsx
  export const Component = () => {

    // TODO: bla...bla...bla
    const Problems = 'Problems';

    return (
      <div>Todo Something...</div>
    );
  };
```

### `CSS/SCSS`

**Note: Instead of using `Color Variables`, do `NOT` use `Color Codes`. If the color code has not been defined. Please leave `TODO` about that.**

```scss
  .a-sample {
    // TODO: Replace with color variable
    color: rgb(0, 0, 0);
  }
```

**Note: Instead of using `Color Rgb`, do `NOT` use `Color Names | Color Hexs | ...`.**

```scss
  //GOOD 🏆🏆🏆
  .a-sample {
    // TODO: Replace with color variable
    color: rgb(0, 0, 0);
  }

  //NOT GOOD 💩💩💩
  .a-sample {
    // TODO: Replace with color variable
    color: black; /* stylelint-disable-line color-named */
  }
```

**Note: Instead of using `@minxin u-fw-*`, do `NOT` use `font-weight`.**

```scss
  //GOOD 🏆🏆🏆
  .a-sample {
    @include u-fw-b;
  }

  //NOT GOOD 💩💩💩
  .a-sample {
    font-weight: bold;
  }
```

**Note: Please use `@function rem` with the properties have dynamic values (Scale-up and Scale-down). rem($SizeOnDesign)**

```scss
  //GOOD 🏆🏆🏆
  .a-sample {
    font-size: rem(16);
    border-radius: 4px;
  }

  //NOT GOOD 💩💩💩
  .a-sample {
    font-size: 16px;
    border-radius: 4px;
  }
```

**Note: Instead of using `@function z`, do `NOT` use `z-index value`. Please define the `zIndex variable` before using that function. Please follow the instructions at `assets/scss/_zIndex.scss`**

```scss
  //GOOD 🏆🏆🏆
  .a-sample {
    z-index: z('headerexam');
  }

  //NOT GOOD 💩💩💩
  .a-sample {
    z-index: 4;
  }
```

### `Storybook`

**Note: Make sure that you have included all instances of the component in the storybook when building it.**

### `Unit Test`

- enzyme: <https://enzymejs.github.io/enzyme/docs/api/>
- jest: <https://jestjs.io/docs/en/25.x/getting-started.html>
- testing-library/react-hooks: <https://react-hooks-testing-library.com/usage/basic-hooks>

**Note: Make full test coverage for the component. If `NOT`, please notify your Leader.**

### `VanillaJS`

<http://vanilla-js.com/>

### `Typescript`

<https://www.typescriptlang.org/index.htm>

### `Redux/Redux-Saga`

- redux: <https://redux.js.org/>
- redux-saga: <https://redux-saga.js.org/>

### `React-router-dom`

<https://reactrouter.com/web/guides/quick-start>

### `Git`

- Rebase: <https://git-scm.com/docs/git-rebase>
- Git branch format: <http://karma-runner.github.io/5.0/dev/git-commit-msg.html>

**Note: When create a new branch. The `type` will include `feature | bugfix | hotfix | release | support`**

```ssh
  git checkout -b type/feature-name
```

**Note: When committed. The `type` will include `feature | bugfix | hotfix | release | support`**

```ssh
  git commit -m 'type(feature-name): messages'
```
