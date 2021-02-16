Testing the recommended TypeScript compiler option `skipLibCheck`.

Run `yarn install` after cloning the repo.

Then run `yarn test` to see the expected compile error.

After that run `yarn test --skipLibCheck`. The compile error is gone

The [documentation](https://www.typescriptlang.org/tsconfig#skipLibCheck) says:

> TypeScript will type check the code you specifically refer to in your app’s
> source code.

What it does not mention, but should not be surprising now that I think about
it, is that any library code that can not be compiled, but your app's source
code refers to, will be regarded as `any`. Even with `noImplicitAny` set to
`true` this does not yield a compile error.
