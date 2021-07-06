

### Option 1 - Script
1. [Setup your environment](https://codelabs.solace.dev/codelabs/codelab-4-codelab/index.html?#1)
1. [Read the solace guidelines](https://codelabs.solace.dev/codelabs/codelab-4-codelab/index.html?#2)
1. From the root directory, run `./init.sh <name-of-codelab>` script
1. Navigate to `/markdown/name-of-codelab`
1. Run the following from terminal `npm install; npm run watch`
1. Edit your `<name-of-codelab>.md` file in your text editor of choice
1. When ready, run `export.sh`
1. Navigate to the codelabs root directory (`cd ../../`), add and commit your changes in a PR. From the root directory,    
```
cd ../../ #to navigate to the root of the codelabs dir
git add .
git commit -m "add new codelab: <name of codelab>"
git push origin add-codelab-<name_of_codelab>
```
Note: _origin_  in the command above the name of the remote repository. If your remote repository is of a different name then you will have to `git push <name_of_remote_repo> add-codelab-<name_of_codelab>`

### Option 2 - Manual

Follow the steps in this tutorial: https://codelabs.solace.dev/codelabs/codelab-4-codelab

Note: original markdown of this codelab is found under [codelabs/codelab-4-codelab](./codelabs/codelab-4-codelab)

## Learn About CodeLab
* CodeLabs are being created using Google Codelabs: https://github.com/googlecodelabs/tools
