# Statistical Learning Theory: Coding Exercises

## Getting Started

### Cloning the repo

To clone the repository, you need to setup the [deploy key](slt2019) first.

Copy the deploy-key to your `~/.ssh/` folder.
    
Sometimes, you need to explicitly add an entry in the `~/.ssh/config`:

```
    Host gitlab.ethz.ch
        IdentityFile ~/.ssh/slt2019
        IdentitiesOnly yes
```

Moreover, if you get permission errors, you should reset the permissions:

```
    chmod 640 ~/.ssh/config
    chmod 640 ~/.ssh/slt2019
```

Finally, clone the repository via ssh (not https!):

```
    git clone git@gitlab.ethz.ch:vwegmayr/slt-coding-exercises-19.git
    cd slt-coding-exercises-19
```

### Creating the environment

Create the [conda](https://conda.io/docs/install/quick.html) environment, which contains the basic packages:

```
    conda env create -n slt-ce -f .environment
```

Activate the environment, and start the notebook:

```
    source activate slt-ce
    jupyter notebook slt-ce-0.ipynb
```
A new browser window with the first exercise should open.

## Complete and submit an exercise

To get the latest exercise, simply pull from the remote repo:

```
    cd slt-coding-exercises-19
    git pull origin master
```

Before you start working on an exercise, you should create a new branch:

```
    git checkout -b 12-345-678/slt-ce-0
```
    
The name of the branch should be your-legi-number/slt-ce-i, where i denotes the respective exercise.

The instructions for each exercise can be found directly in the notebook.

Once you are done, encrypt your notebook:

```
    ./encrypt.sh slt-ce-0.ipynb
    > File encrypted as slt-ce-0.ipynb.encr
```

Then commit and push the encrypted notebook:

```
    git add slt-ce-0.ipynb.encr
    git commit slt-ce-0.ipynb.encr -m "Submit slt-ce-0"
    git push origin 12-345-678/slt-ce-0
```

`You can only submit your notebook before the respective deadline.`

`We accept submissions only via git as described above.`

`Do not push notebooks which are not encrypted.`


## Exercise grading

We offer 8 exercises. Each submitted exercise is graded between 4 and 6.

For admission to the written exam, you need to receive a grade of 4 in at least **five** exercises.

The exercise grade is computed as the average of your best five submissions.

The course grade is the weighted average of written exam and exercise (70%/30%). 

### Example 1

Exercise grades: 5.5, 5.0, 5.0, 6.0, -, -, -, -

Failed course, submitted only four exercises!

### Example 2

Exercise grades: 5.0, 5.5, 5.0, 4.0, 6.0, 6.0, -, -

Exercise grade = (5.0 + 5.0 + 5.5 + 6.0 + 6.0) / 5 = 5.5

Exam grade = 5.0

Course grade = round(0.3 * 5.5 + 0.7 * 5.0) = 5.25


## Exercise deadlines

Hand-Ins are due by **noon** of the respective hand-in day, and the hand-in period typically starts one week earlier.

`Exercises can not be handed in after the deadline, because the server is blocked!`

|   | Exercise                 | Release   |  Hand-In          | 
|---|--------------------------|-----------|-------------------|
| 0 | Test Submission Process  | Feb 18th  | Feb 25th 11:59am  |
| 1 | Locally Linear Embedding | Feb 25th  | Mar 11th 11:59am  |
| 2 | Sampling                 | Mar 11th  | Mar 25th 11:59am  |
| 3 | Deterministic Annealing  | Mar 25th  | Apr  8th 11:59am  |
| 4 | Histogram Clustering     | Apr 8th   | Apr 22nd 11:59am  |
| 5 | Constant Shift Embedding | Apr 22nd  | May  6th 11:59am  |

