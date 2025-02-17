---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "tetration_user Resource - terraform-provider-tetration"
subcategory: ""
description: |-
  Resource for creating a user in Secure Workload (Tetration)
  Example
  An example is shown below:
  hcl
  resource "tetration_user" "new_user" {
      email = "test@domain.com"
      first_name = "test"
      last_name = "user"
      app_scope_id = <ID_OF_SCOPE>
      role_ids = ["<ROLE_IDS>"]
      enable_existing = true 
  }
  
  Note: If creating multiple rules during a single terraform apply, remember to use depends_on to chain the rules so that terraform creates it in the same order that you intended.
---

# tetration_user (Resource)

Resource for creating a user in Secure Workload

## Example
An example is shown below: 
```hcl
resource "tetration_user" "new_user" {
    email = "test@domain.com"
    first_name = "test"
    last_name = "user"
	 app_scope_id = <ID_OF_SCOPE>
    role_ids = ["<ROLE_IDS>"]
    enable_existing = true 
}
```
**Note:** If creating multiple rules during a single `terraform apply`, remember to use `depends_on` to chain the rules so that terraform creates it in the same order that you intended.



<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `email` (String) Email address associated with the user account.
- `first_name` (String) Userʼs first name.
- `last_name` (String) Userʼs last name.

### Optional

- `app_scope_id` (String) (Optional) Root scope to which the user belongs.
- `enable_existing` (Boolean) If true, and an existing but disabled user with the same email exists they will be enabled.
- `role_ids` (Set of String) (Optional) A list of roles to be assigned to the user.

### Read-Only

- `disabled_at` (Number) UNIX timestamp indicating when the user account was disabled. Zero or null if not disabled.
- `id` (String) The ID of this resource.


