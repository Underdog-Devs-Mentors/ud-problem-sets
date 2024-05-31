# Basic applications

## User creation

The point of this exercise is to practice storing and changing user information. Your program should parse JSON data (from a file for now), allowing the following fields to be set via that JSON: `username`, `first-name`, `last-name`, `email`, `password`, `following`, `followers`. These are all strings except `following` and `followers`, which are both lists of strings.

In `/data` you will find a file called `new_user.json`. Create a new user from this data and store it however you'd like (JSON or CSV probably makes sense). You can store this file in `/data` if you'd like.

Your program should also be able to show a list of all existing users, showing their username.

> Question: Is there anything else you think we might want to save for each user?

## (challenge) Editing an existing user

Using the set up from the previous problem, allow a user's list of `following` and `followers` to be updated via JSON.

In `/data` you will find a file named `add_follower.json` to do this with. You should update the appropriate list for both uses.

Make sure that the user being followed exists before adding it to the list! Your program should print the new list at the end.
