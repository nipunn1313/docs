# Updating a mid-stack branch

{% hint style="info" %}
Stacked changes aren't just about adding more branches on top - sometimes you want to go back and change something mid-stack.  Graphite makes it easy to update a mid-stack branch, and automatically rebases the changes you have stacked on top.
{% endhint %}

## Adding commits

Let's say you receive some comments in code review that you want to address with a new commit before landing a branch in the middle of your stack - here's how you'd do this with `gt`:

```bash
# address review comments with a new commit
gt branch checkout my_stack_level_1
gt commit create -a -m "my fourth commit" # -> automatically rebases both upstack branches
```

![Graphite will automatically perform the recursive rebases if you have up-stack changes when you run gt commit create on a mid-stack branch.](../../.gitbook/assets/Untitled.png)

## Amending commits

If you prefer to go back and amend a previous commit, this is just as easy with `gt`:

```bash
# address review comments by amending a commit
gt branch checkout my_stack_level_1
gt commit amend -a -m "my updated commit" # -> automatically rebases both upstack branches
```

Now that you can create, navigate, and update stacks, it's time to turn them into pull requests!
