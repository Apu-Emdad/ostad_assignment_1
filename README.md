**1. Set Up a Local Git Repository:**

```js
mkdir assingnment_1
```

```js
touch README.md
```

make necessary changes in `README.md`

```js
git init
```

**2. Create a New GitHub Repository:**

o Create a new repository on GitHub - `ostad_assignment_1`

```js
git remote add origin git@github.com:Apu-Emdad/ostad_assignment_1.git
```

o Push your local commits to the GitHub repository.

```js
git add .
git commit -m "Initial Commit - README.md created"
git push -u origin master
```

**3. Branching:**

o Create a new branch in your local repository called “dev”.

```js
git checkout -b dev
```

o Switch to your new branch and create a new file called  **hello.txt**.

```js
touch hello.txt
```

o Commit the changes to your new branch.

```js
git commit -m "hello.txt created"
```

**4. Pushing the New Branch:**

o Push your new branch to GitHub, making sure it's reflected in your remote repository.

```js
git add .
git commit -m "Initial Commit - README.md created"
git push -u origin dev
```

o Verify that your new branch is visible on GitHub.



**5. Create a Pull Request:**

o Once the new changes have been committed and pushed, go to your GitHub repository.

o Open a pull request to merge your new branch into the main branch.

o Provide a description of the changes you made in the pull request.



**6. Merge the Pull Request:**

o After reviewing your pull request, merge the pull request into the main branch on GitHub.

o Ensure that your local main branch is updated after the merge.
