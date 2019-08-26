# Command Line Interface



## Ontology CLI

### Installation

The Ontology CLI is a part of the [core Ontology repository](https://github.com/ontio/ontology). Download the core Ontology protocol repository and install all dependencies in the proper directory `$GOPATH/src/github.com/ontio`

```text
git clone https://github.com/ontio/ontology.git
```

or

```text
go get github.com/ontio/ontology
```

Navigate to the local repository

```text
cd $GOPATH/src/github.com/ontio
```

Install project dependencies

```text
glide install
```

Build from source code

```text
make all
```

