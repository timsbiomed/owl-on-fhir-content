# `owl-on-fhir-content`
Static OWL content, pre and post converted to FHIR.

## Running conversions manually
Another repository is set up to do this automaticaly. However, for reference, the steps to do so are here.

We are using https://github.com/incATools/ontology-access-kit/ to do the conversion.

### Option A: Latest release
```sh
$ pip install oaklib
$ runoak -i OWL_PATH dump -o OUTPATH -O fhirjson --include-all-predicates
```

### Option B: Latest code in development
```sh
# `poetry` is a Python package manager that OAK uses
$ pip install poetry

$ git clone https://github.com/INCATools/ontology-access-kit.git; cd ontology-access-kit

# `poetry shell` creates a virtual environment if one does not exist, and activates it
$ poetry shell

$ poetry install

# As of 2022/12/06, `origin/fhir-updates` is a currently open development branch. It may be that `main` also has updates that haven't yet made it to release, so you could try running from that branch. If `origin/fhir-updates` is already closed/merged, you can look to see if there are any other open FHIR-related branches https://github.com/INCATools/ontology-access-kit/pulls 
$ git checkout origin/fhir-updates

$ python src/oaklib/cli.py -i OWL_PATH dump -o OUTPATH -O fhirjson --include-all-predicates
```

## Data sources
Latest releases can be found at the following locations.
- CompLOINC: TODO
- go-nucleus: TODO
- HPO: https://github.com/obophenotype/human-phenotype-ontology/releases/latest/download/hp-full.owl
- Mondo: https://github.com/monarch-initiative/mondo/releases/latest/download/mondo.owl