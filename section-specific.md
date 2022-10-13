---
layout: page
parent: 📖 Resources
title: Accessing section-specific data
nav_exclude: True
---

# Accessing section-specific data

Some mentors have coordinated with the methodology staff and DSMLP to provide **only** the students in their section access to data on DSMLP. This data lives in section-specific folders that only the students in their section have access to.

Here's how to launch a server on DSMLP in a way that you can access this section-specific data. For the purposes of this example, we will assume you want to use the vanilla `launch-scipy-ml.sh` launch script, but these steps work with any launch script and flags. Also, note that here "team" and "section" mean the same thing; by "team" we don't mean your project's team.

1. `ssh` onto DSMLP as usual. Don't run any launch scripts yet.
2. Run `launch-scipy-ml.sh -W DSC180A_FA22_A00 -G list`. Note that this won't actually launch a server – instead, this will list all of the groups you are a part of. You should see a row that contains your capstone section number for the "Team," like `DSC 180A - A14 [88137]` in the example below. **Copy the "Team ID"** (`dsc180aa1488137100014352` in the example below).

<center><img src="../assets/images/team-login-1.png" width="75%"></center>

**Note:** If you don't see the right team information at this step, contact Suraj.

3. Run `launch-scipy-ml.sh -W DSC180A_FA22_A00 -G <teamid>`, with `<teamid>` replaced with the Team ID you copied earlier. If you're in section A14 like in the example above, you'd run `launch-scipy-ml.sh -W DSC180A_FA22_A00 -G dsc180aa1488137100014352`.

4. After your server launches, run `ls`. You should see three folders – `private`, `public`, and `teams`. Your home directory is in `private` (that's where all your code should live). The `public` folder contains files that the methodology course staff may share with the entire course. 

5. To find your section-specific data, `cd` into `teams`. Run `ls` to see a list of all of the teams in the course and identify the name of yours. This may look like the example below. If, again, you're in section A14, your team-specific folder is `"dsc-180a---a14-[88137]"` (the quotes are important). If you `cd` into that folder, you'll see the files that your mentor uploaded for you!

<center><img src="../assets/images/team-login-2.png" width="75%"></center>

All you need to do now is access the data in your team's folder from your code in the `private` folder! For instance, from a script at the root of your `private` folder, a path to a file in your team's folder might be `"../teams/dsc-180a---a14-[88137]/example.txt"`.