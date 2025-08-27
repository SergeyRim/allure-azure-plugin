This extension allows you to use `$(Build.BuildNumber)` and optionally `$(Build.DefinitionName)` to distinguish between Allure reports for different pipelines. 

In the original extension, only `$(Build.BuildNumber)` is allowed, so if, for example, two different pipelines generate and upload Allure reports in the same run, both report files will be mixed in one folder (i.e., 20250827.1). With the additional `$(Build.DefinitionName)` variable, we can set baseUrl to https://some-url/$(Build.DefinitionName)/$(Build.BuildNumber), so each pipeline will have its own Allure folder.

Build with:
`tfx extension create --manifest-globs vss-extension.json`
