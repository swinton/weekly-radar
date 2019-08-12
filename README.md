# Weekly Radar

## Usage
This GitHub Action will try to find the first open issue with a `radar` label, close it, and link it to a newly created Weekly Radar template issue. Finally, it will assign the new issue to `ASSIGNEES`.

```
name: Weekly Radar
on:
  schedule:
  - cron: 0 12 * * 1

jobs:
  weekly_radar:
    name: Close Old and Open New Weekly Radar
    runs-on: ubuntu-latest
    steps:

    - name: weekly-radar
      uses: imjohnbo/weekly-radar@master
      with:
        assignees: "some space delimited list of assignees"
```

## Miscellaneous

* `schedule(*,*,*,*,*)` is just [one option](https://developer.github.com/actions/managing-workflows/creating-and-cancelling-a-workflow/#scheduling-a-workflow) based on cron schedules. Knock yourself out by instead responding to [events](https://developer.github.com/actions/managing-workflows/workflow-configuration-options/#events-supported-in-workflow-files)!
* `env.ASSIGNEES` is a space delimited list of assignees for the new issue.

## Contributing
Feel free to open an issue, or better yet, a pull request!

## License
[MIT](https://choosealicense.com/licenses/mit/)

