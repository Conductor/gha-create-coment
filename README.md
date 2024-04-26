# gha-create-coment
GitHub composite action to create paginated comments in purpose to handle GH limits


GitHub limits comment to 65K chars, what could not enough in case of Terraform plane or other massive output.   


To workaround that limit the comment text should be dumped to a file and pass to GH action.  
Using github-script the comment will be split on chunks and commented one by one.    

Usage:
```yaml
steps:
  - uses: Conductor/gha-create-coment@main
    with:
      title: Title
      summary: summary
      filename: comment.txt
      github_token: ${{ secrets.GITHUB_TOKEN }}

```

