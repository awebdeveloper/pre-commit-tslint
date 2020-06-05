Pre-commit hook for TSlint
========================

This is the TSlint hook for [pre-commit](https://github.com/pre-commit/pre-commit). This prevents git commits unless the checks pass. 


### Usage

- To use this you first need to install pre-commit(see links below). 
- Then create a pre-commit config file and also the linter config file in the root of your project. 
- Run `pre-commit install` from the root of your project

Finally add this to your `.pre-commit-config.yaml`:

```yaml
    -   repo: git://github.com/awebdeveloper/pre-commit-tslint/
        rev: ''  # Use the sha or tag you want to point at
        hooks:
        -   id: tslint
            additional_dependencies: ['tslint@5.0.0']
 ```
PS: These are for version 2.3.0 visit https://pre-commit.com/#2-add-a-pre-commit-configuration for latest config syntax or for config syntax specific to your version

 
 Now everytime you commit a ts file. It will run tslint on this and prevent commit if the checks fail.
 
 
### FAQs 
- To use with ```tslint-eslint-rules``` include it as `additional_dependencies`

- To check type or if linter complaints of type include the following args (but this will slow down your commit)
```yaml
     hooks:
        -   id: tslint
            args: ['--project','tsconfig.json','--type-check']
```


 ### Links
 - For pre-commit: see https://github.com/pre-commit/pre-commit

 - For stylelint: see https://github.com/palantir/tslint



        
   
