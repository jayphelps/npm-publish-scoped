# npm-publish-scoped

Publish any package temporarily to your `@user` scope, while you wait for them cut a release. Useful when your PR is merged and you don't want to wait.

## Install

```
npm install -g npm-publish-scoped
```

## Usage

You must first have a valid npm user account and be logged in on your machine. See [npm instructions on logging in](https://docs.npmjs.com/cli/adduser).

Navigate to the project you want to publish and make sure you've run any build commands! If you don't build the project first, you'll publish outdated or missing artifacts!

Inside the project, just run:

```
npm-publish-scoped
```

Now the package will be available at `@username/package-name` under the `next` tag (aka version). Then you'll install that temporary package in your project with:

```
npm install @username/package-name@next --save

# or

npm install @username/package-name@next --save-dev
```

### Customize the user scope

If you want to publish it under a different scope than your npm username, you can pass in the scope as the only argument

```
npm-publish-scoped custom-scope
```

You must have permission to publish to that scope, and it will always be published as `--access public`