
# UI/UX

## Key Ideas

* UI = User Interface
  * Screen by screen (or webpage by webpage or audio dialogue) data content and arrangement
  * Navigation (menus, page-to-page 1:M navigation, links)
  * Common framework items (banners, menu structure, common services like Forex conversions or language selection)
  
* UX = User eXperience
  * Overall "look and feel" of interface
  * Colors, fonts and graphics
  * Overall visual organization or framework
  * More art than science: Often created by an IT graphic artist

## UI Design

* Two fundamental types of systems:
  * **Online Transaction Processing (OLTP)**:
    * Creating and processing individual data transactions
      * Retail websites (orders)
      * Payroll (paychecks)
      * Accts. Payable (invoices and payments)
      * Health care claims processing (health care claims)
  * **Data/Business analytics/reporting**
    * Turning OLTP transactions into information
      * Tabular reports
      * Charts/Graphs
      * Online dashboards

## OLTP UI Design

* Data:
  * Data elements and labels (text boxes, drop downs, reference selectors, etc.)
  * Specific arrangement (single column, double column, sections, tab order)
* Navigation
  * Menus
  * Page-to-page 1:M based
  * Hyperlinks
* Framework elements:
  * Common to all screens
    * Banners
    * Login/password resets
    * Conversions (e.g. language, currencies)
    * Common links (e.g. to static pages, Contact Us, Help, Careers, etc.)

## General UX/UI Framework

* Typically adopted early on in an application lifecycle
* **General Layout**
  * Banner, logo, sizing, fixed vs. dynamic sizing, bread crumbs
  * Visual styles via CSS
* **Common functions and capabilities**: Forex conversions, language localization, standard data to display for any:
  * Table: Table name
  * Row: E.g. SegID (if intranet), Added By with Date/Time, Changed By with Date/Time and/or logging
* **General data entry layout standards**: E.g.:
  * Single column
  * Double column
  * USe of outline (+ sign) or accordian/dropdown button
  
## UI Modeling Fidelity

* **Fidelity**: The degree of exactness with which a UI model corresponds in all respects to the finished product
* **Need for high fidelity UI models**
  * Increased fidelity requires increased time and effort
  * Implementation of UX and UI frameworks creates reusable patterns and reduces need for fidelity
* **UI modeling choices**
  * Wireframe:
    * Low-fidelity model
    * Outlines basic visual representation of design
  * Sketch:
    * Essentially a hand-drawn wireframe
    * Acceptability of "just barely good enough" models like sketches has risen with rise of agile approaches
  * Mockup:
    * High-fidelity graphic design diagram
    * Looks more like a finished product or prototype
    * But not interactive or clickable
  * Prototype:
    * Similar high-fidelity to a mockup
    * Generally interactive or clickable (screen-to-screen or within screen)
    * As such, processes and user interaction can be simulated and user interaction can be tested
    * **_May or may not_** be re-used for production code
    * Mendix could be considered a prototype

## Deriving Screens from the Domain Model

* **Rule of thumb:** Every entity/table needs two screens
  * Overview/Data List screen:
    * Display multiple objects/records
    * Search function
    * Edit/Delete existing object/record vs. Create new object/record
    * Navigate to corresponding NewEdit/Data View screen
  * NewEdit/Data View screen
    * Navigation from Display single object/records
    * Add/Update/Delete
  * Hybrid screen
    * Combining a NewEdit/Data View screen with one (or more) associated Overview/Data List Screen(s)

## 1:M Relationships: Hybrid Screens vs. Reference Selectors

* **Hybrid screen:**
  * NewEdit/ Data view screen "1 side" with embedded Overview/Data List "many side"
  * Often advisable when 1:M relationship is a parent/child
    * More than an "updatable enumeration"
    * E.g. Client/Employee, Employee/Dependent, Patient/Medical Visit, etc.
  * May have multiple Overview/Data Lists on a single Data View if entity has more than one significant 1:M parent/child relationships
* **Reference selector fields**:
  * A different kind of 1:M relationship
  * "1 side" of this a list of values used in (potential many) "Many side" entities, e.g.:
    * List of states or provinces
    * In the Training Management example app, for "ScheduledCourse", reference selectors include "Trainer", "Course", and "Location"
    * Note that a reference selector (AKA a lookup or setup table) is essentially a more flexible version of an enumeration dropdown field (values can be added/modified by business users)

## Smartphones and Tablets


* Challenges
  * Small screen size
  * Small keyboards and touch screens
  * Limited network capacity
  * Different app design guidelines and tool-kits
* Responsive web pages:
  * Common today
  * Means web page will automatically resize to fit available screen size
  * But frequently less-than-stellar outcomes
* Issues
  * Example: Menus
    * Hamburger menu:
      * AKA side menu or navigation drawer
      * De facto convention on many apps
    * Criticized for:
      * Hiding too many menu options
      * Hard to reach if at top left
    * Alternatives
      * The tab menu
      * Tab menu with a hamburger
* **Mobile Website vs App**
  * Mobile website:
    * Browser-based (same as regular websites)
    * Can display text, structured data, images, video
    * Can also access some mobile-specific features (e.g. click-to-call, location-based mapping)
  * Apps:
    * Actual applications downloaded and installed on mobile device
    * From Apple App Store, Google Play Store, etc.
    * Ability to pull content from Internet back ends (like websites) AND/OR download content accessible without internet connection
    * Better than a website for
      * Games and other apps needing interactivity (e.g. music or video generations or editing)
      * Accessing mobile device native capabilities (e.g. device camera)

# Use Cases, User Stories, and Use Case Slices

## User Stories

* In **_agile development_**, user stories serve as the primary mechanism for
  * Capturing a user's idea of a feature that will produce value
  * Articulating product backlog items
* Standard format: "As a \<type of user\>, I want \<a goal\> so that \<statement of value\>"
* Level of abstraction varies significantly
  * Specific user goal
  * Broad expression of an end-to-end business process

## Epics

* Epics are user stories at a high level, describing overall goals for a system
  * Business process level (e.g. an entire swim lane diagram)
  * Other meaningful groupings, e.g.
    * Groups of ETL mappings from multiple external entities
    * Integration points with a new workflow system
    * Etc.
* Epics are too broad to serve as product backlog items; instead, they will have to be split into/elaborated with multiple, smaller user stories

## Use Case Narratives

* Text document describing a set of functional requirements - how the system works from a user's perspective - associated with a specific user goal
* Originated with software engineering, rather than agile approaches
* UML Use Case Diagram different from Use Case Narrative
* UML does NOT specify a specific format for a use case narrative
* Use Case Narrative synonymous with Use Case Description
* One of the most commonly used mechanisms for specifying functional requirements
* **Three Use Case Narrative/Description Formats**
  * **Brief** - one paragraph summary - very similar in detail to a user story
  * **Casual** - informal multi-paragraph format
  * **Fully Dressed** - a detailed, formally structured description included multiple scenarios, preconditions, and success guarantees
  * NOTE: These are just 3 specific possibilities - it is entirely possible to define other format variations to suit a given situation

## User Stories vs Use Case Narratives

* Why we do use case narratives in the first place
  * Diagrams (Activity Diagrams, Class Diagrams/ERDs, UI/UX designs) don't capture enough detail
  * User stories also lack detail (even with acceptance criteria)
  * **Another benefit of Use Case Narratives:** Hub-and-Spoke integration of related requirements
    * Use Cases are the hub
    * Spokes:
      * Performance requirements
      * I/O Protocols
      * Data formats
      * UI Requirements
      * UI Design
      * Business Rules

## Splitting/Slicing

* Work needs to fit into individual sprints
* **Step 1: Splitting an Epic Based on Actor Transitions**
  * Basic Splitting Technique
    1. Spit by primary actor (generally only happens if corresponding user story is at epic level)
    2. Split by enabling technology
    3. Split by size using use case basic and extension/alternate scenarios within a fully dressed use case
* **Step 2: Using Fully Dressed Use Cases to Further Slice Up the Work**
  * Use Case Slice
    * For a given overall use case, refers to specific pathways through main success scenario and extensions
    * For small/simple use cases, mat have only one slice
    * For large/complex use cases, may have many slices
    * Can be used as backlog items
    * Assist finding the application architecture
  * Simple Approach to Slicing
    * Main scenario/basic flow is Slice 1
    * Alternate scenario(s)/extensions is/are Slices 2 and beyond

## Use Case Diagrams vs. Use Case Narratives

* A mechanism for cataloging use cases and showing their core relationships
* Confusion between UC Diagrams vs. UC Narratives
* Use Case Diagrams
  * UML standard
  * Mostly useful in outlining user stories or use case narratives needed
  * A "standard" that is not used much, if at all

# Cost Estimation

## Fundamental Challenges of Estimation

* **The Planning Fallacy:** Systematic tendency to
  * Underestimate effort and costs of development
  * Overestimate business benefits
* **Absolute Project Size:**
  * Large size magnifies impacts of the Planning Fallacy
  * Large projects are (also) more visible and sensitive to blow back from being X% over budget
* **Tension between Agility and Planning:**
  * Agile approach emphasizes launching projects based on (literally) a series of "one-liner" stories

## Estimating Development Costs

* **Development Costs:** If significant internal development
  * Typically high cost category by far
  * Hardest cost category to estimate accurately by far
  * Highest risk - if development estimate is significantly low, then project is typically doomed before it even starts
* **Hallmarks of Good Estimates:**
  * Accurate rather than precise
  * Is stable over time for a fundamental amount of scope
* **Examples:**
  * Good estimate: $1M-$1.2M, turns out to be $1.2M with minimal trimming of "Nice to Have" scope

## The Cone of Uncertainty

* Represents the _best_ skilled software estimators can do
* It is always possible to do worse!
* The cone:
  * Does _not_ always narrow over time
  * If requirements or designs change, the cone can _widen_ over time!
* Overarching messages:
  * Makes sense to estimate costs as high as possible early in the cone
  * This fundamentally similar to the concept of padding
  * Selling management on progressive reviews is smart
    * If organization is sufficiently "agile"
    * May be a way to open management eyes to realities of uncertainty without "drinking the agile Kool-Aid"
  
## Cost Estimating Approaches

* Used for:
  * Project visioning
  * Project business case approvals
  * Ongoing cost/benefit evaluations throughout project (sometimes)
* **Typical approaches:** Roughly from least effort/accurate to most effort/accurate
  * T-shirt Sizing
  * Planning Poker
  * Development Expert Opinion
  * Function Points or Lines of Code
  * Software Tools (e.g. COCOMO II)
  * Elaboration/Decomposition/Segmentation

## T-Shirt Sizing: Weeding Out Features based on "Directionally Meaningful" Estimates

* Juxtaposing Business Value vs. Software Features
  * "Directionally meaningful," rather than precise (or even accurate)
  * A way to help weed out features that are simply infeasibly large and costly in comparison to business expenses

## Planning Poker: Achieving Consensus while Avoiding Group Think

* **Typically associated with agile development methods**
* **Asks each developer in secret:**
  * In your judgement, how many development days (or story points) should it take to complete series of stories?
  * May use planning poker decks or just write down on slips of paper
  * Typically decks using Fibonacci numbers: 1, 2, 3, 5, 8, 13, 21, 34, 55, or 89 days
  * Supposed to reflect inherent uncertainty of estimating
* **Importance of making judgements in secret:**
  * Avoids cognitive bias of anchoring
  * First number spoken aloud sets a precedent for subsequent estimates

## Developer Expert Opinion

* Not really a "method"
* Simply asks a BA and developer expert to "guesstimate" based on:
  * Summary description of a feature/story
  * Any insights the BA can offer, e.g.:
    * Acceptance criteria
    * Ability to leverage existing application features or architecture
    * Important areas of flexibility and/or reusability
  * Any insights the developer expert can offer, e.g.:
    * Technology risks (e.g. integration of a new enabling technology)
    * Availability (or not) of key developers who have deep expertise in this functionality/sub-system/module
* Possible to use this for business case sizing:
  * Decomposition: Ensure epics broken down into stories
  * Take into account Planning Fallacy
  * Padding to push to upper half of Cone of Uncertainty

## Function Points

* **Can create a standard effort estimate based on counting:**
  * **External Inputs:** Screens, forms, dialogs through which user or other program adds, deletes, or changes data
  * **External Outputs:** Screens, reports, graphs that program generates for use by a user or other program
  * **External Queries:** Retrieving data directly from DB with minimal formatting
  * **Internal Logical Files:** Typically a single flat file or a table in an RDBMS
  * **External Interface Files:** That enter from or leave to another program
* **Function Points in Context**
  * Requires (fairly) detailed designs
  * Therefore:
    * Appropriate for BRUF approaches (e.g. Hybrid or Waterfall)
    * Cannot be easily applied to Emergent Requirements approaches (e.g. agile methods such as Scrum, XP, etc.)
* Function Points work _ceteris paribus_ "All other things being equal"
* But every software project is unique
* Generically, consider the project in terms of 3 general dimensions:
  * **People:** Experienced and cohesive vs. new and divided?
  * **Product:** Extensions to a known, functional application vs. development of a new class of system?
  * **Process:**
    * Transitioning from Traditional SDLC to Agile (at least first one or two releases)?
    * Trying to merge two teams who historically have used different processes?

## Using Modeling to Adjust Levels of Effort

* Ex: COCOMO II
  * COnstructive COst MOdel
  * Developed by software engineering team at USC
  * Provides adjustments to estimates based on numerous "Effort Multiplier adjustment factors
  * Each range from:
    * Very Low
    * Low
    * Nominal
    * High
    * Very High
    * Extra High
  * COCOMO II Effort Multipliers especially relevant to People/Product/Process
    * People:
      * Requirements Analyst Capability (100% impact!)
      * Applications (Business Area) Experience
      * Programmer General Capability
      * Language and Tools Experience
      * Platform Experience (code base)
      * Multi-Site Development (56% swing in effort!)
      * Personnel Turnover
      * Team Cohesion
    * Product:
      * Product Complexity (138% impact!)
      * (Un)Precendentedness
    * Process:
      * Process Maturity

## Unadjusted vs. Adjusted Function Points

* Some controversy about how to adjust level of complexity of various Program Characteristics:
  * What's "Low"?
  * What's "Medium"?
  * What's "High"?
* Difficulty in determining subjective values for "turning the dials"
* Evidence that unadjusted function points are as good or better than adjusted function points
  * Just assume every Program Characteristic is "Medium"
  * Eliminate "dial turning"
  * Eliminates sources of subjectivity
* Real issue is whether up-front estimates ultimately turn out to closely match actual cost expenditures

## General Techniques for Improving Cost and Effort Estimates

* **Combatting Planning Fallacy:**
  * **Segmentation:** Break scope down into small "chunks" or segments and estimate each segment separately
  * **Scope management via acceptance criteria:** Estimate for "Must Haves", "Should Haves", and (if possible) "Nice to Haves", then defend delivery of "Must Haves"
  * **Beware of large absolute scope:**
    * Large projects fail 3 to 5 times more frequently
    * Take the time to estimate in detail
* **Risk Management:**
  * **RUP approach:** Attack known technology/requirements risks first
  * **Use POCs to mitigate technology risks:** Build "throwaway" proof of concepts
* **3 Ps:** Whether using software models or not
  * **Honestly assess threats:** from changes in People, Process, and Product
  * **Build in additional costs:** for overcoming these factors
  * **Mitigating product risks via POCs: Build "throwaway" proof of concept projects to prove that a new technology will work or be successfully integrated
* **Estimate fixed costs as fixed:** Often, specific team roles other than developers are de facto fixed and should be costed so
  * **Project leads and project managers**
  * **Business Analysts**
  * **UI/UX specialists**
  * **Testers**
  * **Operations/deployment team**
* **Assess actual velocity:** Compared to assumed velocity
  * **Measure total delivery effort:** This is NOT the "classic" agile approach
  * **Include bug fixing and refactoring:** These are classic velocity problems
  * **Build reference data sets:** If we estimated 100 dev days for the last project and spent 200+, then don't blindly trust estimation in the current project
  * **Developer-by-developer assessments:** Where developers on a team vary greatly in terms of costs and capability, take that into account

## Estimating Business Value: The Basics

* 3 fundamental ways to use IT to increase business value:
  * increase efficiency by decreasing operational costs
    * decrease hours required to deliver product or service
    * decrease mixed rate of operations team (e.g. more junior, less skilled users)
  * Increase revenue:
    * Increase revenue of non-IT products and services sold
      * Increase product/service quality
      * increase features (or a brand new product)
    * Increase revenue directly via selling software
      * Custom software development consulting model
      * COTS products
        * On-premises licenses
        * Cloud-based SaaS fees
      * Maintenance fees
  * Increase ad revenue when "giving away" the IT product
* Staying in business: When IT solution is integral to the business
  * Regulatory compliance: E.g. complying legal audits
  * Privacy and security: Esp. for PI and PII
  * Keeping enabling technology current
  * Increasing accessibility through architecting for reliability