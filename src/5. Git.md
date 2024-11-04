# Git

```plantuml

@startuml

title Git Workflow Overview

!define RECTANGLE(x) rectangle x as x

RECTANGLE(GitHubOrganization) {
    :Organization created;
    :Members added;
    :All members made owners;
}

RECTANGLE(GitRepo) {
    :Git repo created in the organization;
}

RECTANGLE(Members) {
    :All members fork the organization repo;
    :All members clone this fork to VS Code;
    :Make changes here;
    :Commit changes locally;
    :Push to their own repo;
    :Send a pull request to the organization's repo;
}

RECTANGLE(Merge) {
    :One of the members merges the pull request;
}

RECTANGLE(Update) {
    :When starting to code, a member's repo is first updated based on the organization repo;
    :Then the member does a local pull;
    :And starts making changes again;
}

@enduml


