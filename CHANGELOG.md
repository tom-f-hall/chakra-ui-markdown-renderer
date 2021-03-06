# Changelog

All notable changes to this project will be documented in this file.

## [1.1.0] - 2021-02-05

### Major Changes

- Now List type are using `UnorderedList` and `OrderedList` components according to providing type.
- Fixes `List`s `spacing` wrong property. Changes `24` to `2`.

If you want to use old List's, just extend defaults and change `List` key with this:

```
list: props => {
  const { start, ordered, children, depth } = props;
  let styleType = 'disc';
  if (ordered) styleType = 'decimal';
  if (depth === 1) styleType = 'circle';
  return (
    <List
      spacing={24}
      as={ordered ? 'ol' : 'ul'}
      styleType={styleType}
      pl={4}
    >
      {children}
    </List>
);
```

## [1.0.0] - 2020-12-16

### Added

- Library now uses `rollup` as a bundler.

### 🔥💥 Breaking Changes

- No more using `@chakra-ui/core` like Chakra-UI did. We're using `@chakra-ui/react` instead of `@chakra-ui/core`
- `@chakra-ui/react` and other dependencies that used by `@chakra-ui/react` now added as peerDependency. You should add `@emotion/react @emotion/styled framer-motion` packages to your project.

## [0.2.0] - 2020-04-17

### Added

- Ability to extend defaults. Allow users to pass in an object as parameter and extend defaults.
