Field Name                  |  SQL Type       |  Description
----------------------------|-----------------|-------------------------
OBJECTID                    |  integer  primary key   autoincrement  not null,      |
FOD_ID                      |  int32          |  Global unique identifier
FPA_ID                      |  text(100)      |  Unique identifier that contains information necessary to track back to the original record in the source dataset
SOURCE_SYSTEM_TYPE          |  text(255)      |  Type of source database or system that the record was drawn from (federal, nonfederal, or interagency)
SOURCE_SYSTEM               |  text(30)       |  Name of or other identifier for source database or system that the record was drawn from



NWCG_REPORTING_AGENCY       |  text(255)      |  Active National Wildlife Coordinating Group (NWCG) 
                            |                 |  Unit Identifier for the agency preparing the fire report 
                            |                 |  (BIA = Bureau of Indian Affairs, 
                            |                 |  BLM = Bureau of Land Management, 
                            |                 |  BOR = Bureau of Reclamation, 
                            |                 |  DOD = Department of Defense, 
                            |                 |  DOE = Department of Energy, 
                            |                 |  FS = Forest Service, 
                            |                 |  FWS = Fish and Wildlife Service, 
                            |                 |  IA = Interagency Organization, 
                            |                 |  NPS = National Park Service, 
                            |                 |  ST/C&L = State, County, or Local Organization
                            |                 |  TRIBE = Tribal Organization)

NWCG_REPORTING_UNIT_ID      |  text(255)      |  Active NWCG Unit Identifier for the unit preparing the fire report.

NWCG_REPORTING_UNIT_NAME    |  text(255)      |  Active NWCG Unit Name for the unit preparing the fire report

SOURCE_REPORTING_UNIT       |  text(30)       |  Code for the agency unit preparing the fire report, based on code/name in the source dataset.

SOURCE_REPORTING_UNIT_NAME  |  text(255)      |  Name of reporting agency unit preparing the fire report, based on code/name in the source dataset.

LOCAL_FIRE_REPORT_ID        |  text(255)      |  Number or code that uniquely identifies an incident report for a particular reporting unit and a particular calendar year.

LOCAL_INCIDENT_ID           |  text(255)      |  Number or code that uniquely identifies an incident for a particular local fire management organization within a particular calendar year.

FIRE_CODE                   |  text(10)       |  Code used within the interagency wildland fire community to track and compile cost information for emergency fire suppression (https://www.firecode.gov/).

FIRE_NAME                   |  text(255)      |  Name of the incident, from the fire report (primary) or ICS-209 report (secondary).

ICS_209_INCIDENT_NUMBER     |  text(255)      |  Incident (event) identifier, from the ICS-209 report.

ICS_209_NAME                |  text(255)      |  Name of the incident, from the ICS-209 report.

MTBS_ID                     |  text(255)      |  Incident identifier, from the MTBS perimeter dataset.

MTBS_FIRE_NAME              |  text(50)       |  Name of the incident, from the MTBS perimeter dataset.

COMPLEX_NAME                |  text(255)      |  Name of the complex under which the fire was ultimately managed, when discernible.

FIRE_YEAR                   |  int16          |  Calendar year in which the fire was discovered or confirmed to exist.

DISCOVERY_DATE              |  realdate       |  Date on which the fire was discovered or confirmed to exist.

DISCOVERY_DOY               |  int32          |  Day of year on which the fire was discovered or confirmed to exist.

DISCOVERY_TIME              |  text(4)        |  Time of day that the fire was discovered or confirmed to exist.

STAT_CAUSE_CODE             |  float64        |  Code for the (statistical) cause of the fire.

STAT_CAUSE_DESCR            |  text(100)      |  Description of the (statistical) cause of the fire.

CONT_DATE                   |  realdate       |  Date on which the fire was declared contained or otherwise controlled (mm/dd/yyyy where mm=month, dd=day, and yyyy=year).

CONT_TIME                   |  text(4)        |  Day of year on which the fire was declared contained or otherwise controlled.

FIRE_SIZE                   |  float64        |  Time of day that the fire was declared contained or otherwise controlled (hhmm where hh=hour, mm=minutes).

FIRE_SIZE_CLASS             |  text(1)        |  Estimate of acres within the final perimeter of the fire.
                            |                 |  Code for fire size based on the number of acres within the final fire perimeter expenditures 
                            |                 |  A=greater than 0 but less than or equal to 0.25 acres
                            |                 |  B=0.26-9.9 acres
                            |                 |  C=10.0-99.9 acres
                            |                 |  D=100-299 acres
                            |                 |  E=300 to 999 acres
                            |                 |  F=1000 to 4999 acres
                            |                 |  G=5000+ acres
LATITUDE                    |  float64        |  Latitude (NAD83) for point location of the fire (decimal degrees)

LONGITUDE                   |  float64        |  Longitude (NAD83) for point location of the fire (decimal degrees).

OWNER_CODE                  |  float64        |  Code for primary owner or entity responsible for managing the land at the point of origin of the fire at the time of the incident.

OWNER_DESCR                 |  text(100)      |  Name of primary owner or entity responsible for managing the land at the point of origin of the fire at the time of the incident.

STATE                       |  text(255)      |  Two-letter alphabetic code for the state in which the fire burned (or originated), based on the nominal designation in the fire report.

COUNTY                      |  text(255)      |  County, or equivalent, in which the fire burned (or originated), based on nominal designation in the fire report.

FIPS_CODE                   |  text(255)      |  Three-digit code from the Federal Information Process Standards (FIPS) publication 6-4 for representation of counties and equivalent entities.

FIPS_NAME                   |  text(255)      |  County name from the FIPS publication 6-4 for representation of counties and equivalent entities. 

