.PHONY: help book clean serve

help:
	@echo "Please use 'make <target>' where <target> is one of:"
	@echo "  install     to install the necessary dependencies for jupyter-book to build"
	@echo "  book        to convert the `content/` folder into Jekyll markdown in `_build/`"
	@echo "  clean       to clean out site build files"
	@echo "  runall      to run all notebooks in-place, capturing outputs with the notebook"
	@echo "  serve       to serve the repository locally with Jekyll"

install:
	gem install bundler
	bundle install
	
book:
	python scripts/license.py --path ./content
	python scripts/generate_book.py

runall:
	python scripts/execute_all_notebooks.py

clean:
	python scripts/clean.py

serve:
	bundle exec guard

deploy:
	bundle exec jekyll build
	rm -rf docs; cp -r _site docs
	echo "Deployed to the docs/ folder"

test:
	pytest scripts/teststest_build.py