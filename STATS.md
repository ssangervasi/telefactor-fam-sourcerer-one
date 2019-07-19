# Git Log

```
commit 6ba928c6758ae806b39e4a3f51cdb175f71e110a
Author: Sebastian Sangervasi <ssangervasi@squareup.com>
Date:   Thu Jul 18 18:17:29 2019 -0700

    Init with tests and no source
```

# CLOC


cloc|github.com/AlDanial/cloc v 1.82  T=0.05 s (737.4 files/s, 32523.5 lines/s)
--- | ---

Language|files|blank|comment|code
:-------|-------:|-------:|-------:|-------:
Ruby|28|208|180|996
Markdown|7|68|0|125
Bourne Again Shell|1|6|0|35
JSON|1|0|0|27
YAML|1|6|10|15
--------|--------|--------|--------|--------
SUM:|38|288|190|1198

# Spec Results
## Fam

```

Fam
  dev apology
    Sorry, rspec is new to me and I did not have my laptop for half the week. \
        Please forgive weirdness!
  add_person
    adding a person
      returns a success message (FAILED - 1)
      returns a SUCCESS_CODE status (FAILED - 2)
    falling asleep on the keyboard and repeatedly adding the person
      raises a DuplicatePerson error (FAILED - 3)
  get_person
    when the area is deserted of people
      returns an error (FAILED - 4)
      returns an ERROR_CODE status
    when the person exists
      returns no error
      returns the person (FAILED - 5)
      returns a SUCCESS_CODE status (FAILED - 6)
  add_parents
    when no one exists
      returns an error for one of the so-called people involved (FAILED - 7)
      returns no output
      returns an ERROR_CODE status
    when the child does not exist
      returns an error for the child being AWOL (FAILED - 8)
      returns no output
      returns an ERROR_CODE status
    when the parents do not exist
      returns an error for the child being AWOL (FAILED - 9)
      returns no output
      returns an ERROR_CODE status
    when everyone exists
      returns no error
      returns a success message about the adoption (FAILED - 10)
      returns a SUCCESS_CODE status (FAILED - 11)
    too many parents
      returns an error for third gene-donor (no non-traditional \
          adoptions/mitochrondria donations)
      returns an error message about the adoption (FAILED - 12)
  families
    nuclear
      returns parents of father correctly (FAILED - 13)
    narcissism
      is a valid means of reproduction (FAILED - 14)
    parthenogenesis
      is a valid means of reproduction (FAILED - 15)
    spontaneous generation
      is a valid means of reproduction (FAILED - 16)
    time travel
      is a valid means of reproduction (FAILED - 17)

Failures:

  1) Fam add_person adding a person returns a success message
     Failure/Error: expect(result.output).to include('Added person: 🕵')
       expected "" to include "Added person: 🕵"
     # ./spec/fam/fam_spec.rb:28:in `block (4 levels) in <top (required)>'

  2) Fam add_person adding a person returns a SUCCESS_CODE status
     Failure/Error: expect(result.status).to be SUCCESS_CODE

       expected #<Integer:1> => 0
            got #<Integer:3> => 1

       Compared using equal?, which compares object identity,
       but expected and actual are not the same object. Use
       `expect(actual).to eq(expected)` if you don't care about
       object identity in this example.
     # ./spec/fam/fam_spec.rb:32:in `block (4 levels) in <top (required)>'

  3) Fam add_person falling asleep on the keyboard and repeatedly adding the person raises a DuplicatePerson error
     Failure/Error:
       expect do
         subject.add_person(input_path: input_path, output_path: input_path, person_name: '🕵')
         subject.add_person(input_path: input_path, output_path: input_path, person_name: '🕵')
       end.to raise_error(Fam::Family::Errors::DuplicatePerson)

     NameError:
       uninitialized constant Fam::Family::Errors
       Did you mean?  Errno
     # ./spec/fam/fam_spec.rb:41:in `block (4 levels) in <top (required)>'

  4) Fam get_person when the area is deserted of people returns an error
     Failure/Error: expect(result.error).to include("No such person '🕵' in family")
       expected "" to include "No such person '🕵' in family"
     # ./spec/fam/fam_spec.rb:51:in `block (4 levels) in <top (required)>'

  5) Fam get_person when the person exists returns the person
     Failure/Error: expect(result.output).to eq('🕵')

       expected: "🕵"
            got: ""

       (compared using ==)
     # ./spec/fam/fam_spec.rb:70:in `block (4 levels) in <top (required)>'

  6) Fam get_person when the person exists returns a SUCCESS_CODE status
     Failure/Error: expect(result.status).to be SUCCESS_CODE

       expected #<Integer:1> => 0
            got #<Integer:3> => 1

       Compared using equal?, which compares object identity,
       but expected and actual are not the same object. Use
       `expect(actual).to eq(expected)` if you don't care about
       object identity in this example.
     # ./spec/fam/fam_spec.rb:74:in `block (4 levels) in <top (required)>'

  7) Fam add_parents when no one exists returns an error for one of the so-called people involved
     Failure/Error: expect(result.error).to include("No such person '🔎' in family")
       expected "" to include "No such person '🔎' in family"
     # ./spec/fam/fam_spec.rb:91:in `block (4 levels) in <top (required)>'

  8) Fam add_parents when the child does not exist returns an error for the child being AWOL
     Failure/Error: expect(result.error).to include("No such person '🕵' in family")
       expected "" to include "No such person '🕵' in family"
     # ./spec/fam/fam_spec.rb:124:in `block (4 levels) in <top (required)>'

  9) Fam add_parents when the parents do not exist returns an error for the child being AWOL
     Failure/Error: expect(result.error).to include("No such person '🔎' in family")
       expected "" to include "No such person '🔎' in family"
     # ./spec/fam/fam_spec.rb:148:in `block (4 levels) in <top (required)>'

  10) Fam add_parents when everyone exists returns a success message about the adoption
      Failure/Error: expect(result.output).to eq('Added 🔎 & 🔍 as parents of 🕵')

        expected: "Added 🔎 & 🔍 as parents of 🕵"
             got: ""

        (compared using ==)
      # ./spec/fam/fam_spec.rb:182:in `block (4 levels) in <top (required)>'

  11) Fam add_parents when everyone exists returns a SUCCESS_CODE status
      Failure/Error: expect(result.status).to be SUCCESS_CODE

        expected #<Integer:1> => 0
             got #<Integer:3> => 1

        Compared using equal?, which compares object identity,
        but expected and actual are not the same object. Use
        `expect(actual).to eq(expected)` if you don't care about
        object identity in this example.
      # ./spec/fam/fam_spec.rb:186:in `block (4 levels) in <top (required)>'

  12) Fam add_parents too many parents returns an error message about the adoption
      Failure/Error: expect(result.error).to eq("Child '🕵' can't have more than 2 parents!")

        expected: "Child '🕵' can't have more than 2 parents!"
             got: ""

        (compared using ==)
      # ./spec/fam/fam_spec.rb:216:in `block (4 levels) in <top (required)>'

  13) Fam families nuclear returns parents of father correctly
      Failure/Error: expect(result.status).to be SUCCESS_CODE

        expected #<Integer:1> => 0
             got #<Integer:3> => 1

        Compared using equal?, which compares object identity,
        but expected and actual are not the same object. Use
        `expect(actual).to eq(expected)` if you don't care about
        object identity in this example.
      # ./spec/fam/fam_spec.rb:243:in `block (4 levels) in <top (required)>'

  14) Fam families narcissism is a valid means of reproduction
      Failure/Error: expect(create_family.status).to be SUCCESS_CODE

        expected #<Integer:1> => 0
             got #<Integer:3> => 1

        Compared using equal?, which compares object identity,
        but expected and actual are not the same object. Use
        `expect(actual).to eq(expected)` if you don't care about
        object identity in this example.
      # ./spec/fam/fam_spec.rb:261:in `block (4 levels) in <top (required)>'

  15) Fam families parthenogenesis is a valid means of reproduction
      Failure/Error: expect(create_family.status).to be SUCCESS_CODE

        expected #<Integer:1> => 0
             got #<Integer:3> => 1

        Compared using equal?, which compares object identity,
        but expected and actual are not the same object. Use
        `expect(actual).to eq(expected)` if you don't care about
        object identity in this example.
      # ./spec/fam/fam_spec.rb:278:in `block (4 levels) in <top (required)>'

  16) Fam families spontaneous generation is a valid means of reproduction
      Failure/Error: expect(create_family.status).to be SUCCESS_CODE

        expected #<Integer:1> => 0
             got #<Integer:3> => 1

        Compared using equal?, which compares object identity,
        but expected and actual are not the same object. Use
        `expect(actual).to eq(expected)` if you don't care about
        object identity in this example.
      # ./spec/fam/fam_spec.rb:295:in `block (4 levels) in <top (required)>'

  17) Fam families time travel is a valid means of reproduction
      Failure/Error: expect(create_family1.status).to be SUCCESS_CODE

        expected #<Integer:1> => 0
             got #<Integer:3> => 1

        Compared using equal?, which compares object identity,
        but expected and actual are not the same object. Use
        `expect(actual).to eq(expected)` if you don't care about
        object identity in this example.
      # ./spec/fam/fam_spec.rb:326:in `block (4 levels) in <top (required)>'

Finished in 0.24909 seconds (files took 0.89217 seconds to load)
28 examples, 17 failures

Failed examples:

rspec ./spec/fam/fam_spec.rb:27 # Fam add_person adding a person returns a success message
rspec ./spec/fam/fam_spec.rb:31 # Fam add_person adding a person returns a SUCCESS_CODE status
rspec ./spec/fam/fam_spec.rb:37 # Fam add_person falling asleep on the keyboard and repeatedly adding the person raises a DuplicatePerson error
rspec ./spec/fam/fam_spec.rb:50 # Fam get_person when the area is deserted of people returns an error
rspec ./spec/fam/fam_spec.rb:69 # Fam get_person when the person exists returns the person
rspec ./spec/fam/fam_spec.rb:73 # Fam get_person when the person exists returns a SUCCESS_CODE status
rspec ./spec/fam/fam_spec.rb:90 # Fam add_parents when no one exists returns an error for one of the so-called people involved
rspec ./spec/fam/fam_spec.rb:123 # Fam add_parents when the child does not exist returns an error for the child being AWOL
rspec ./spec/fam/fam_spec.rb:147 # Fam add_parents when the parents do not exist returns an error for the child being AWOL
rspec ./spec/fam/fam_spec.rb:181 # Fam add_parents when everyone exists returns a success message about the adoption
rspec ./spec/fam/fam_spec.rb:185 # Fam add_parents when everyone exists returns a SUCCESS_CODE status
rspec ./spec/fam/fam_spec.rb:215 # Fam add_parents too many parents returns an error message about the adoption
rspec ./spec/fam/fam_spec.rb:241 # Fam families nuclear returns parents of father correctly
rspec ./spec/fam/fam_spec.rb:260 # Fam families narcissism is a valid means of reproduction
rspec ./spec/fam/fam_spec.rb:277 # Fam families parthenogenesis is a valid means of reproduction
rspec ./spec/fam/fam_spec.rb:294 # Fam families spontaneous generation is a valid means of reproduction
rspec ./spec/fam/fam_spec.rb:325 # Fam families time travel is a valid means of reproduction

```

## Boilerplate

```

Fam::CLI::Add::Parents
  when the child and parent names are given
    behaves like a successful command
      exits with a zero status code (FAILED - 1)
      matches the expected output (FAILED - 2)
  when all names are missing
    behaves like a failed command
      exits with a non-zero status code (FAILED - 3)
      matches the expected error (FAILED - 4)

Fam::CLI::Add::Person
  when a name is given
    behaves like a successful command
      exits with a zero status code (FAILED - 5)
      matches the expected output (FAILED - 6)
  when no name is provided
    behaves like a failed command
      exits with a non-zero status code
      matches the expected error

Fam::CLI::Get::Parents
  when a child name is given
    behaves like a successful command
      exits with a zero status code (FAILED - 7)
      matches the expected output (FAILED - 8)
  when the child name is missing
    behaves like a failed command
      exits with a non-zero status code (FAILED - 9)
      matches the expected error (FAILED - 10)

Fam::CLI::Get::Person
  when a name is given
    behaves like a successful command
      exits with a zero status code (FAILED - 11)
      matches the expected output (FAILED - 12)
  when the name is missing
    behaves like a failed command
      exits with a non-zero status code (FAILED - 13)
      matches the expected error (FAILED - 14)

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

Failures:

  1) Fam::CLI::Add::Parents when the child and parent names are given behaves like a successful command exits with a zero status code
     Failure/Error:
       expect(
         Hatchery::Names.simpsons.map do |person_name|
           exec_fam('add', 'person', person_name)
         end
       ).to(
         all(be_success),
         'Must be able to `add person` before testing `get parents`'
       )

       Must be able to `add person` before testing `get parents`
     Shared Example Group: "a successful command" called from ./spec/boilerplate/cli/add/parents_spec.rb:25
     # ./spec/boilerplate/cli/add/parents_spec.rb:14:in `block (2 levels) in <top (required)>'

  2) Fam::CLI::Add::Parents when the child and parent names are given behaves like a successful command matches the expected output
     Failure/Error:
       expect(
         Hatchery::Names.simpsons.map do |person_name|
           exec_fam('add', 'person', person_name)
         end
       ).to(
         all(be_success),
         'Must be able to `add person` before testing `get parents`'
       )

       Must be able to `add person` before testing `get parents`
     Shared Example Group: "a successful command" called from ./spec/boilerplate/cli/add/parents_spec.rb:25
     # ./spec/boilerplate/cli/add/parents_spec.rb:14:in `block (2 levels) in <top (required)>'

  3) Fam::CLI::Add::Parents when all names are missing behaves like a failed command exits with a non-zero status code
     Failure/Error:
       expect(
         Hatchery::Names.simpsons.map do |person_name|
           exec_fam('add', 'person', person_name)
         end
       ).to(
         all(be_success),
         'Must be able to `add person` before testing `get parents`'
       )

       Must be able to `add person` before testing `get parents`
     Shared Example Group: "a failed command" called from ./spec/boilerplate/cli/add/parents_spec.rb:35
     # ./spec/boilerplate/cli/add/parents_spec.rb:14:in `block (2 levels) in <top (required)>'

  4) Fam::CLI::Add::Parents when all names are missing behaves like a failed command matches the expected error
     Failure/Error:
       expect(
         Hatchery::Names.simpsons.map do |person_name|
           exec_fam('add', 'person', person_name)
         end
       ).to(
         all(be_success),
         'Must be able to `add person` before testing `get parents`'
       )

       Must be able to `add person` before testing `get parents`
     Shared Example Group: "a failed command" called from ./spec/boilerplate/cli/add/parents_spec.rb:35
     # ./spec/boilerplate/cli/add/parents_spec.rb:14:in `block (2 levels) in <top (required)>'

  5) Fam::CLI::Add::Person when a name is given behaves like a successful command exits with a zero status code
     Failure/Error: expect(subject.status).to eq(0), (subject.output + subject.error)
     Shared Example Group: "a successful command" called from ./spec/boilerplate/cli/add/person_spec.rb:13
     # ./spec/spec_helpers/cli.rb:28:in `block (3 levels) in <top (required)>'

  6) Fam::CLI::Add::Person when a name is given behaves like a successful command matches the expected output
     Failure/Error: expect(subject.output).to match expected_output
       expected "" to match "José Exemplo"
     Shared Example Group: "a successful command" called from ./spec/boilerplate/cli/add/person_spec.rb:13
     # ./spec/spec_helpers/cli.rb:32:in `block (3 levels) in <top (required)>'

  7) Fam::CLI::Get::Parents when a child name is given behaves like a successful command exits with a zero status code
     Failure/Error:
       expect(
         Hatchery::Names.simpsons.map do |person_name|
           exec_fam('add', 'person', person_name)
         end
       ).to(
         all(be_success),
         'Must be able to `add person` before testing `get parents`'
       )

       Must be able to `add person` before testing `get parents`
     Shared Example Group: "a successful command" called from ./spec/boilerplate/cli/get/parents_spec.rb:33
     # ./spec/boilerplate/cli/get/parents_spec.rb:14:in `block (2 levels) in <top (required)>'

  8) Fam::CLI::Get::Parents when a child name is given behaves like a successful command matches the expected output
     Failure/Error:
       expect(
         Hatchery::Names.simpsons.map do |person_name|
           exec_fam('add', 'person', person_name)
         end
       ).to(
         all(be_success),
         'Must be able to `add person` before testing `get parents`'
       )

       Must be able to `add person` before testing `get parents`
     Shared Example Group: "a successful command" called from ./spec/boilerplate/cli/get/parents_spec.rb:33
     # ./spec/boilerplate/cli/get/parents_spec.rb:14:in `block (2 levels) in <top (required)>'

  9) Fam::CLI::Get::Parents when the child name is missing behaves like a failed command exits with a non-zero status code
     Failure/Error:
       expect(
         Hatchery::Names.simpsons.map do |person_name|
           exec_fam('add', 'person', person_name)
         end
       ).to(
         all(be_success),
         'Must be able to `add person` before testing `get parents`'
       )

       Must be able to `add person` before testing `get parents`
     Shared Example Group: "a failed command" called from ./spec/boilerplate/cli/get/parents_spec.rb:43
     # ./spec/boilerplate/cli/get/parents_spec.rb:14:in `block (2 levels) in <top (required)>'

  10) Fam::CLI::Get::Parents when the child name is missing behaves like a failed command matches the expected error
      Failure/Error:
        expect(
          Hatchery::Names.simpsons.map do |person_name|
            exec_fam('add', 'person', person_name)
          end
        ).to(
          all(be_success),
          'Must be able to `add person` before testing `get parents`'
        )

        Must be able to `add person` before testing `get parents`
      Shared Example Group: "a failed command" called from ./spec/boilerplate/cli/get/parents_spec.rb:43
      # ./spec/boilerplate/cli/get/parents_spec.rb:14:in `block (2 levels) in <top (required)>'

  11) Fam::CLI::Get::Person when a name is given behaves like a successful command exits with a zero status code
      Failure/Error:
        expect(exec_fam('add', 'person', person_name))
          .to(
            be_success,
            'Must be able to `add person` before testing `get person`'
          )

        Must be able to `add person` before testing `get person`
      Shared Example Group: "a successful command" called from ./spec/boilerplate/cli/get/person_spec.rb:21
      # ./spec/boilerplate/cli/get/person_spec.rb:10:in `block (2 levels) in <top (required)>'

  12) Fam::CLI::Get::Person when a name is given behaves like a successful command matches the expected output
      Failure/Error:
        expect(exec_fam('add', 'person', person_name))
          .to(
            be_success,
            'Must be able to `add person` before testing `get person`'
          )

        Must be able to `add person` before testing `get person`
      Shared Example Group: "a successful command" called from ./spec/boilerplate/cli/get/person_spec.rb:21
      # ./spec/boilerplate/cli/get/person_spec.rb:10:in `block (2 levels) in <top (required)>'

  13) Fam::CLI::Get::Person when the name is missing behaves like a failed command exits with a non-zero status code
      Failure/Error:
        expect(exec_fam('add', 'person', person_name))
          .to(
            be_success,
            'Must be able to `add person` before testing `get person`'
          )

        Must be able to `add person` before testing `get person`
      Shared Example Group: "a failed command" called from ./spec/boilerplate/cli/get/person_spec.rb:31
      # ./spec/boilerplate/cli/get/person_spec.rb:10:in `block (2 levels) in <top (required)>'

  14) Fam::CLI::Get::Person when the name is missing behaves like a failed command matches the expected error
      Failure/Error:
        expect(exec_fam('add', 'person', person_name))
          .to(
            be_success,
            'Must be able to `add person` before testing `get person`'
          )

        Must be able to `add person` before testing `get person`
      Shared Example Group: "a failed command" called from ./spec/boilerplate/cli/get/person_spec.rb:31
      # ./spec/boilerplate/cli/get/person_spec.rb:10:in `block (2 levels) in <top (required)>'

Finished in 13.81 seconds (files took 1.73 seconds to load)
20 examples, 14 failures

Failed examples:

rspec ./spec/boilerplate/cli/add/parents_spec.rb[1:1:1:1] # Fam::CLI::Add::Parents when the child and parent names are given behaves like a successful command exits with a zero status code
rspec ./spec/boilerplate/cli/add/parents_spec.rb[1:1:1:2] # Fam::CLI::Add::Parents when the child and parent names are given behaves like a successful command matches the expected output
rspec ./spec/boilerplate/cli/add/parents_spec.rb[1:2:1:1] # Fam::CLI::Add::Parents when all names are missing behaves like a failed command exits with a non-zero status code
rspec ./spec/boilerplate/cli/add/parents_spec.rb[1:2:1:2] # Fam::CLI::Add::Parents when all names are missing behaves like a failed command matches the expected error
rspec ./spec/boilerplate/cli/add/person_spec.rb[1:1:1:1] # Fam::CLI::Add::Person when a name is given behaves like a successful command exits with a zero status code
rspec ./spec/boilerplate/cli/add/person_spec.rb[1:1:1:2] # Fam::CLI::Add::Person when a name is given behaves like a successful command matches the expected output
rspec ./spec/boilerplate/cli/get/parents_spec.rb[1:1:1:1] # Fam::CLI::Get::Parents when a child name is given behaves like a successful command exits with a zero status code
rspec ./spec/boilerplate/cli/get/parents_spec.rb[1:1:1:2] # Fam::CLI::Get::Parents when a child name is given behaves like a successful command matches the expected output
rspec ./spec/boilerplate/cli/get/parents_spec.rb[1:2:1:1] # Fam::CLI::Get::Parents when the child name is missing behaves like a failed command exits with a non-zero status code
rspec ./spec/boilerplate/cli/get/parents_spec.rb[1:2:1:2] # Fam::CLI::Get::Parents when the child name is missing behaves like a failed command matches the expected error
rspec ./spec/boilerplate/cli/get/person_spec.rb[1:1:1:1] # Fam::CLI::Get::Person when a name is given behaves like a successful command exits with a zero status code
rspec ./spec/boilerplate/cli/get/person_spec.rb[1:1:1:2] # Fam::CLI::Get::Person when a name is given behaves like a successful command matches the expected output
rspec ./spec/boilerplate/cli/get/person_spec.rb[1:2:1:1] # Fam::CLI::Get::Person when the name is missing behaves like a failed command exits with a non-zero status code
rspec ./spec/boilerplate/cli/get/person_spec.rb[1:2:1:2] # Fam::CLI::Get::Person when the name is missing behaves like a failed command matches the expected error

```

