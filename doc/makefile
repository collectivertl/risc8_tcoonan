all: doc

doc: pdf html

pdf:
	sphinx-build -M latexpdf . ./_build/pdf

html:
	sphinx-build -b html . ./_build/html

clean:
	rm -rf _build
	rm -f ./images/risc8.jpg
