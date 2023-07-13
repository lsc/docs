# Using Infracost

{% hint style="info" %}
This feature is in early development. If you find something that can be improved, please let us know by [filing an issue](https://github.com/diggerhq/digger/issues)
{% endhint %}

You can configure Digger to use Infracost to estimate cloud costs.

## Pre-requisites

Infracost binary needs to be installed into your CI pipeline (see [Infracost docs](https://www.infracost.io/docs/integrations/generic\_cicd/))

## Digger.yml configuration

```
projects:
  - name: project_a_d
    dir: ./project_a/development
    workflow: project_a

workflows:
  project_a:
    plan:
      steps:
        - init
        - plan
        - run: infracost breakdown --path=.
```

## See cost estimate output

After the pipeline run finishes, you should see Infracost breakdown output in your CI job logs:

<figure><img src="../.gitbook/assets/infracost-example.png" alt=""><figcaption></figcaption></figure>
