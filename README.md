
1. From the root directory, run `./init.sh <name-of-codelab>` script
2. Navigate to `/markdown/name-of-codelab`
3. Run the following from terminal `npm install; npm run watch`
4. Edit your `<name-of-codelab>.md` file in your text editor of choice
5. When ready, run `export.sh`
6. Navigate to the codelabs root directory (`cd ../../`), add and commit your changes in a PR. From the root directory,    
```
cd ../../ #to navigate to the root of the codelabs dir
git add .
git commit -m "add new codelab: <name of codelab>"
git push origin add-codelab-<name_of_codelab>
```
Note: _origin_  in the command above the name of the remote repository. If your remote repository is of a different name then you will have to `git push <name_of_remote_repo> add-codelab-<name_of_codelab>`

### Option 2 - Manual

run `./export.sh`