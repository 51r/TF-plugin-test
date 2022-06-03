# Custom Kitchen-CI test

This repo contains Kitchen-CI test that uses Kitchen-Terraform and InSpec to verify the Terraform Configuration and custom plugin on Linux_amd64 Environment. 

The test uses cmp matcher and it will verify if the output IP is shown and if differs from the loopback IP (127.0.0.1). 

# Prerequisites

1. Linux Ubuntu AMD 64 environment
2. [Ruby](https://www.ruby-lang.org/en/downloads/)
3. [bundler](https://bundler.io/)
4. [Terraform](https://www.terraform.io/downloads)

*note: The Linux Ubuntu amd64 env is required, as the plugin was compiled for the following architecture. If you wish you can download and compile for different architecture by using the following guide: [Terraform-custom-plugin](https://github.com/51r/terraform-custom-plugin)*

# How to use the Kitchen-CI test

1. Download the repo: 
 ```
git clone https://github.com/51r/TF-plugin-test.git
 ```

2. Make sure you are in the main of the project:
```
cd TF-plugin-test
```

3. Install the Ruby gems from the Gemfile with bundler:
```
bundle install
```
4. Build the Kitchen-CI environment:
```
bundle exec kitchen converge
```

5. Run the test:

```
bundle exec kitchen test
```
The above command will init terraform, apply the plan, test and then destroy the terraform plan.

You should see the following output:

<img width="560" alt="Screen Shot 2022-06-03 at 11 34 01 AM" src="https://user-images.githubusercontent.com/52199951/171819187-f96cdc38-edc5-4693-b622-e782b693e6e7.png">
