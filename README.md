## Entities
**PROPERTY** - A PROPERTY has any number of AMENITIES, can be picked by any number of RENTERS, and listed by any number of AGENTS. Each PROPERTY is exactly one CLASS. Any number of OFFERS can be made on the PROPERTY. Each property is identified by prop_id.
**AMENITY** - An AMENITY is had by any number of PROPERTIES, and can be picked by any number of RENTERS. An AMENITY is uniquely identified by its amen_id.
**RENTER** - A RENTER can pick any number of PROPERTIES and AMENITIES, and is exactly one CLASS. Each renter is uniquely identified by renter_id. 
**CLASS** - A CLASS classes any number of PROPERTIES or RENTERS. Each CLASS is uniquely identified by its class_id. Each class_id is a single uppercase character, A, B, or C.
**AGENT** - Each AGENT lists any number of PROPERTIES and has exactly one PACKAGE. Each AGENT is uniquely identified by agent_id.
**OFFER** - Each OFFER is made by exactly one AGENT to exactly one RENTER on exactly one PROPERTY. They are uniquely identified by offer_id.
**PACKAGE** - Each PACKAGE is had by any number of AGENTS. PACKAGES are uniquely identified by package_name.

### Associative Entities
**PROP_AMEN_LIST** - A PROP_AMEN has exactly one PROPERTY associated with it and any number of AMENITIES associated with it. They are weak entities, identified uniquely by prop_id.
**PROP_AGENT_LIST** - A PROP_AGENT has exactly one PROPERTY associated with it and any number of AGENTS associated with it. They are weak entities, identified by prop_id.
**PROP_CLASS_LIST** - A PROP_CLASS has exactly one PROPERTY and CLASS associated with it. They are weak entities, identified by prop_id.
**RENTER_AMEN_LIST** - A RENTER_AMEN has exactly one RENTER associated with it and any number of AMENITIES associated with it. They are weak entities, identified by renter_id
**RENTER_PROP_LIST** - A RENTER_PROP has exactly one RENTER associated with it and any number of PROPERTIES associated with it. They are weak entities, identified by renter_id
**RENTER_CLASS_LIST** - A RENTER_CLASS has exactly one RENTER associated with it and zero or one CLASSES associated with it. They are weak entities, identified by renter_id.
**AGENT_PACKAGE_LIST** - A AGENT_PACKAGE has exactly one AGENT and exactly one PACKAGE associated with it. They are weak entities, identified by agent_id. Additionally, they record the pkg_period.

## Relationships

## Assumptions

* Can **PROPERTIES** have no **AMENITIES**? - YES
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
    * offer_id
    * offer_desc
    * offer_expr
    * offer_status
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
