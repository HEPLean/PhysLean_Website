# The PhysLean Website
This repository hosts the website for PhysLean. 
It is currently under development. For now please visit: heplean.com 


The PhysLean website is made using [Jekyll](https://jekyllrb.com) and is generated via the workflow
`./.github/docs.yml`.

## Hosting the website locally

The installation instructions for jekyll can be found [here](https://jekyllrb.com/docs/installation/#requirements).

Once jekyll is installed:
- Clone this repo
- navigate your terminal to the `./Site` directory of your clone using e.g. `cd ./Site`.
- Run `bundle exec jekyll serve`
- Open `http://localhost:4000` in your web browser.

## Updating dependencies 

```
cd ./Site 
rm Gemfile.lock 
bundle install
```
## PhysLean domain

The PhysLean website is hosted at `https://physlean.com`. This domain is registered via
squarespace domains by Joseph Tooby-Smith.
