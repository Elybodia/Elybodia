TTE DATABASE postgresql://thomas_nse0_user:DNcjvbg1wtgeAW8hPvxLwUIEYTOTgbZe@dpg-cse5hcjtq21c73850jvg-a.oregon-postgres.render.com/thomas_nse0
on:

push:

branches:

- main

pull_request:

branches:

- main

jobs:

build:

runs-on: ubuntu-latest

strategy:

matrix:

node-version: [20.x]

steps:

- name: Checkout repository

uses: actions/checkout@v3

- name: Set up Node.js

uses: actions/setup-node@v3

with:

node-version: ${{ matrix.node-version }}

- name: Install dependencies

run: npm install

- name: Start application

run: npm start