# GMI GitLab Merge Process

- [ ] Check status of current branch. Ensure working tree is clean.

    ``` git status ```

- [ ] Switch to "dev" branch.
    
    ``` git checkout dev ```

- [ ] Check status of "dev" branch. Ensure working tree is clean.
    
    ``` git status ```

- [ ] Fetch branch needing to be merged to "dev" branch.
    
    ``` git fetch git@ec2-35-168-28-94.compute-1.amazonaws.com:spitfire/phase-4.git [BRANCH NAME]:[BRANCH NAME]  ```

- [ ] Merge new branch into "dev" branch
    
    ``` git merge [BRANCH NAME] ```

- [ ] Push merged changes back to repository
    
    ``` git push ```

- [ ] Create new branch for continued development
    
    ``` git checkout -b [NEW BRANCH NAME] ```

- [ ] Switch to env.local
    
    ``` . .env.local ```

- [ ] Run NPM build script
    
    ``` npm run build ```

- [ ] Run NPM serve script
    
    ``` npm run serve ```
    
