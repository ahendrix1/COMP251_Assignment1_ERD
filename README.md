## Entities
**PROPERTY**
**AMENITY**
**RENTER**
**CLASS**
**AGENT**
**OFFER**
**PACKAGE**

### Associative Entities
**PROP_AMEN_LIST**
**PROP_AGENT_LIST**
**PROP_CLASS_LIST**
**RENTER_AMEN_LIST**
**RENTER_PROP_LIST**
**RENTER_CLASS_LIST**
**AGENT_PACKAGE_LIST**

## Relationships

## Assumptions

* Can **RENTERS** exist without a **PROFILE**? - NO, a public profile is required to be a renter account.
* Can **AGENTS** also have a **PROFILE**? - NO, an agent account cannot have a renting profile.
* Can **RENTERS** make **OFFERS**? - NO, only agent accounts can make offers.
* Do **RENTERS** have associated locations or addresses? - NO, they are people.
* Can an **AGENT** have more than one **PACKAGE**? - NO, agent accounts can only have one package.

## Attributes
### **PROPERTY**
    * prop_id
    * prop_address
    * prop_firstname
    * prop_lastname
    * prop_email
    * prop_phone
    * prop_shortdesc
    * prop_longdesc
    * prop_location
    * prop_range
    * prop_sqrft
### **AMENITY**
    * amen_id
    * amen_name
    * amen_desc
### **RENTER**
    * renter_id
    * renter_firstname
    * renter_lastname
    * renter_email
    * renter_phone
    * renter_range
### **CLASS**
    * class_title
    * class_desc
    * class_id
### **AGENT**
    * agent_id
    * agent_status
### **OFFER**
### **PACKAGE**
    * pkg_name
    * pkg_desc
## Associative Attributes
### **PROP_AMEN_LIST**
    * prop_id
    * amen_id
### **PROP_AGENT_LIST**
    * prop_id
    * agent_id
### **PROP_CLASS_LIST**
    * prop_id
    * class_id
### **RENTER_AMEN_LIST**
    * renter_id
    * amen_id
### **RENTER_PROP_LIST**
    * renter_id
    * prop_id
### **RENTER_CLASS_LIST**
    * renter_id
    * class_id
### **AGENT_PACKAGE_LIST**
    * agent_id
    * pkg_id
    * pkg_period
