# Git Log

```
commit fbeebee852700c0fddff3b15a3a1df027dc171b3
Author: Jon Whiteaker <jbw@squareup.com>
Date:   Fri Jul 26 08:40:25 2019 -0600

    Jon's sourcery
```

# CLOC


cloc|github.com/AlDanial/cloc v 1.82  T=0.04 s (1068.5 files/s, 50837.7 lines/s)
--- | ---

Language|files|blank|comment|code
:-------|-------:|-------:|-------:|-------:
Ruby|28|230|180|1127
Markdown|7|68|0|125
Bourne Again Shell|1|6|0|35
YAML|1|6|10|15
JSON|1|0|0|6
--------|--------|--------|--------|--------
SUM:|38|310|190|1308

# Spec Results
## Fam

```

Fam
  dev apology
    Sorry, rspec is new to me and I did not have my laptop for half the week. \
        Please forgive weirdness!
  add_person
    adding a person
      returns a success message
      returns a SUCCESS_CODE status
    falling asleep on the keyboard and repeatedly adding the person
      raises a DuplicatePerson error (FAILED - 1)
  get_person
    when the area is deserted of people
      returns an error
      returns an ERROR_CODE status
    when the person exists
      returns no error
      returns the person
      returns a SUCCESS_CODE status
  add_parents
    when no one exists
      returns an error for one of the so-called people involved
      returns no output
      returns an ERROR_CODE status
    when the child does not exist
      returns an error for the child being AWOL
      returns no output
      returns an ERROR_CODE status
    when the parents do not exist
      returns an error for the child being AWOL
      returns no output
      returns an ERROR_CODE status
    when everyone exists
      returns no error
      returns a success message about the adoption
      returns a SUCCESS_CODE status
    too many parents
      returns an error for third gene-donor (no non-traditional \
          adoptions/mitochrondria donations)
      returns an error message about the adoption
  families
    nuclear
      returns parents of father correctly
    narcissism
      is a valid means of reproduction
    parthenogenesis
      is a valid means of reproduction
    spontaneous generation
      is a valid means of reproduction
    time travel
      is a valid means of reproduction

Failures:

  1) Fam add_person falling asleep on the keyboard and repeatedly adding the person raises a DuplicatePerson error
     Failure/Error:
       expect do
         subject.add_person(input_path: input_path, output_path: input_path, person_name: '🕵')
         subject.add_person(input_path: input_path, output_path: input_path, person_name: '🕵')
       end.to raise_error(Fam::Family::Errors::DuplicatePerson)

       expected Fam::Family::Errors::DuplicatePerson but nothing was raised
     # ./spec/fam/fam_spec.rb:38:in `block (4 levels) in <top (required)>'

Finished in 0.11449 seconds (files took 0.87149 seconds to load)
28 examples, 1 failure

Failed examples:

rspec ./spec/fam/fam_spec.rb:37 # Fam add_person falling asleep on the keyboard and repeatedly adding the person raises a DuplicatePerson error

```

## Boilerplate

```

Fam::CLI::Add::Parents
  when the child and parent names are given
    behaves like a successful command
      exits with a zero status code
      matches the expected output
  when all names are missing
    behaves like a failed command
      exits with a non-zero status code
      matches the expected error

Fam::CLI::Add::Person
  when a name is given
    behaves like a successful command
      exits with a zero status code
      matches the expected output
  when no name is provided
    behaves like a failed command
      exits with a non-zero status code
      matches the expected error

Fam::CLI::Get::Parents
  when a child name is given
    behaves like a successful command
      exits with a zero status code
      matches the expected output
  when the child name is missing
    behaves like a failed command
      exits with a non-zero status code
      matches the expected error

Fam::CLI::Get::Person
  when a name is given
    behaves like a successful command
      exits with a zero status code
      matches the expected output
  when the name is missing
    behaves like a failed command
      exits with a non-zero status code
      matches the expected error

Fam::File::Reader::JSONReader
  #read
    when the file does not exist
      raises an error
    when the file exists
      should be a kind of Hash

Fam::File::Writer::JSONWriter
  #write
    should be a kind of String
    modifies the specified file

Finished in 14.56 seconds (files took 0.48442 seconds to load)
20 examples, 0 failures

```

