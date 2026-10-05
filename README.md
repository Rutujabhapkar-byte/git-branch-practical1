Sure. Let's do it **step-by-step from the beginning**, in a simple practical format. You can follow each step and tell me **“next”** after completing it.

## Step 1: Open your GitHub Repository

1. Open [GitHub](https://github.com/?utm_source=chatgpt.com).
2. Open the repository where you want to create the GitHub Actions workflow.
3. Make sure your project is already pushed to GitHub.

Your repository may look like:

```text
my-project
├── README.md
├── index.html
└── ...
```

---

## Step 2: Create the `.github` folder

Inside your GitHub repository:

1. Click **Add file**.
2. Select **Create new file**.
3. In the filename box, type:

```text
.github/workflows/workflow.yml
```

GitHub will automatically create the `.github` and `workflows` folders.

You should see:

```text
.github/
   workflows/
      workflow.yml
```

---

## Step 3: Add the workflow code

Paste this code into `workflow.yml`:

```yaml
name: Build Test Deploy

on:
  push:
    branches:
      - main

jobs:
  build-test-deploy:
    runs-on: ubuntu-latest

    steps:

      - name: Checkout Code
        uses: actions/checkout@v4

      - name: Build
        run: echo "building....."

      - name: Test
        run: echo "testing....."

      - name: Deploy
        run: echo "deploying....."
```

### What this code means

**Workflow name:**

```yaml
name: Build Test Deploy
```

This is the name you'll see under the **Actions** tab.

**Trigger:**

```yaml
on:
  push:
    branches:
      - main
```

This means the workflow will automatically run whenever you **push code to the `main` branch**.

**Runner:**

```yaml
runs-on: ubuntu-latest
```

GitHub provides an Ubuntu virtual machine to run the workflow.

**Build step:**

```yaml
- name: Build
  run: echo "building....."
```

It prints:

```text
building.....
```

**Test step:**

```yaml
- name: Test
  run: echo "testing....."
```

It prints:

```text
testing.....
```

**Deploy step:**

```yaml
- name: Deploy
  run: echo "deploying....."
```

It prints:

```text
deploying.....
```

---

## Step 4: Commit the workflow

Scroll down to the bottom of the GitHub page.

You'll see **Commit changes**.

Enter:

```text
Add GitHub Actions workflow
```

Then click:

**Commit changes**

Now the workflow file is stored in your repository.

---

## Step 5: Open Actions

At the top of your repository, click:

**Actions**

You should see:

```text
Build Test Deploy
```

Click it.

You should see a workflow run with a yellow/green status.

---

## Step 6: Check the execution

Click the workflow run.

Then click:

**build-test-deploy**

You should see the steps:

```text
✓ Checkout Code
✓ Build
✓ Test
✓ Deploy
```

Click **Build**.

You should see:

```text
building.....
```

Click **Test**.

You should see:

```text
testing.....
```

Click **Deploy**.

You should see:

```text
deploying.....
```

---

## Step 7: Final verification

Your final result should be:

```text
Build Test Deploy
        │
        ▼
  Checkout Code
        │
        ▼
      Build
        │
        │  building.....
        ▼
      Test
        │
        │  testing.....
        ▼
     Deploy
        │
        │  deploying.....
        ▼
    Workflow ✓
```

If all steps show a **green check mark ✓**, your practical is successfully completed.

### Practical result

**Result:** Successfully created and executed a GitHub Actions workflow containing **Build, Test, and Deploy** steps, and verified their execution through the GitHub **Actions** tab.
