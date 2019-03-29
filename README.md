# SQL::Abstract::More::Common

## NAME

SQL::Abstract::More::Common - Construct common SQL queries

## SYNOPSIS

```perl
use SQL::Abstract::More::Common;

my ($stmt, @bind) = INSERT(
    -into   => 'Books',
    -values => {
        title => 'Perl 5,
        isbn  => '9780596004927',
    }
);
my $sth = $dbh->prepare($stmt);
$sth->execute(@bind);
```
But mre convenient:
```perl
use SQL::Abstract::More::Common;

$dbh->do_UPDATE(
    -table  => 'Books',
    -values => { title => 'Programming Perl' },
    -where  => { isbn => '9780596004927' },
);
```

## DESCRIPTION

This module provides convenience for constructing and excecuting most
common SQL commands. It is mstly a wrapper around methods inside
`SQL::Abstract::More`.

## METHODS

The following methods return a `$stmt` string and a list for `@bind` values.
They are intended to be used in `prepare` and `execute`.

### INSERT

### DELETE

### UPDATE

### SELECT

For more convenience, the following methods are added to the DBI namespace,
such that they can be called directly on $dbh.

### do_INSERT

### do_DELETE

### do_UPDATE

### do_SELECT_all_hashref



