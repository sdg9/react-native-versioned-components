This project demonstrates react native, using yarn to version components in a monorepo.


### With Metro bundler doesn't seem like workspaces is required to use them

1. packages/component-A exists w/ it's own packages json
2. app-mobile exists as another node packages, referencing component-A
   1. run `npm install` from app-mobile, now changes in `component-A` are linked locally to app-mobile.
   2. run `npm start` from app-mobile and load packager `http://localhost:8081/index.bundle?platform=android&dev=true` or app and see that it references the component-A without a single workspace config
      1. This may be why when I think i'm using workspaces, it always prefers local resolutions over remote, even when there is a local version mismatch but perfect remote match
