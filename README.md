<img width="996" height="589" alt="image" src="https://github.com/user-attachments/assets/e7e7b8d1-d33f-4a0c-a521-ad33f94ed029" />
## Entities

**PROPERTY** - A PROPERTY has any number of AMENITIES, can be picked by any number of RENTERS, and listed by any number of AGENTS. Each PROPERTY is exactly one CLASS. Any number of OFFERS can be made on the PROPERTY. Each property is identified by prop_id.

**AMENITY** - An AMENITY is had by any number of PROPERTIES, and can be picked by any number of RENTERS. An AMENITY is uniquely identified by its amen_id.


**RENTER** - A RENTER can pick any number of PROPERTIES and AMENITIES, and is exactly one CLASS. A RENTER can have any number of OFFERS made to them. Each renter is uniquely identified by renter_id. 

**CLASS** - A CLASS classes any number of PROPERTIES or RENTERS. Each CLASS is uniquely identified by its class_id. Each class_id is a single uppercase character, A, B, or C.

**AGENT** - Each AGENT lists any number of PROPERTIES and has exactly one PACKAGE. Each AGENT is uniquely identified by agent_id.

**OFFER** - Each OFFER is made by exactly one AGENT to exactly one RENTER on exactly one PROPERTY. They are uniquely identified by offer_id.

**PACKAGE** - Each PACKAGE is had by any number of AGENTS. PACKAGES are uniquely identified by package_name.

### Associative Entities

**PROP_AMEN_LIST** - A PROP_AMEN has exactly one PROPERTY associated with it and exactly one AMENITY associated with it. They are weak entities, identified uniquely by prop_id and amen_id.

**PROP_AGENT_LIST** - A PROP_AGENT has exactly one PROPERTY associated with it and exactly one AGENTS associated with it. They are weak entities, identified by prop_id and agent_id.

**RENTER_AMEN_LIST** - A RENTER_AMEN has exactly one RENTER associated with it and exactly one AMENITY associated with it. They are weak entities, identified by renter_id and amen_id.

**RENTER_PROP_LIST** - A RENTER_PROP has exactly one RENTER associated with it and exactly one PROPERTY associated with it. They are weak entities, identified by renter_id and prop_id

**AGENT_PACKAGE_LIST** - A AGENT_PACKAGE has exactly one AGENT and exactly one PACKAGE associated with it. They are weak entities, identified by agent_id. Additionally, they record the pkg_period.


## Relationships

A **PROPERTY** <ins>has</ins> zero, one, or multiple **AMENITIES**, **AMENITIES** are had by zero, one, or multiple **PROPERTIES**.

A **PROPERTY** <ins>has</ins> zero, one, or multiple **OFFERS**, **OFFERS** are made on exactly one **PROPERTY**.

A **RENTER** <ins>picks</ins> zero, one, or multiple **PROPERTIES**, **PROPERTIES** are picked by zero, one, or multiple **RENTERS**.

A **RENTER** <ins>picks</ins> zero, one, or multiple **AMENITIES**, **AMENITIES** are picked by zero, one, or multiple **RENTERS**.

A **RENTER** <ins>has</ins> zero, one, or multiple **OFFERS**, **OFFERS** are made to exactly one **RENTER**.

A **CLASS** <ins>classifies</ins> one or multiple **RENTER**, a **RENTER** has exactly one **CLASS**

A **CLASS** <ins>classifies</ins> one or multiple **PROPERTY**, a **PROPERTY** has exactly one **CLASS**.

An **AGENT** <ins>lists</ins> zero, one, or multiple **PROPERTIES**, **PROPERTIES** are listed by zero, one, or multiple **AGENTS**.

An **AGENT** <ins>makes</ins> zero, one, or multiple **OFFERS**, **OFFERS** are made by exactly one **AGENT**.

An **AGENT** <ins>has</ins> exactly one **PACKAGE**, a **PACKAGE** is had by zero, one, or multiple **AGENTS**.


A **PROPERTY** has zero, one, or multiple **PROP_AMEN_LIST**, which is had by zero, one, or multiple **AMENITIES**.

A **PROPERTY** has zero, one, or multiple **PROP_AGENT_LIST**, which is had by zero, one, or multiple **AGENTS**.

A **RENTER** has zero, one, or multiple **RENTER_PROP_LIST**, which is had by zero, one, or multiple **PROPERTIES**.

A **RENTER** has zero, one, or multiple **RENTER_AMEN_LIST**, which has zero, one, or multiple **AMENITIES**.

A **AGENT** has exactly one **AGENT_PACKAGE_LIST**, which has exactly one **PACKAGE**.



## Assumptions

* Can **PROPERTIES** have no **AMENITIES**? - YES

* Can **RENTERS** exist without a **PROFILE**? - NO, a public profile is required to be a renter account.

* Can **AGENTS** also have a **PROFILE**? - NO, an agent account cannot have a renting profile.

* Can **RENTERS** make **OFFERS**? - NO, only agent accounts can make offers.

* Do **RENTERS** have associated locations or addresses? - NO, they are people.

* Can an **AGENT** have more than one **PACKAGE**? - NO, agent accounts can only have one package.

