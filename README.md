# The Description of Zospital Istanbul Database Project:
Zospital Istanbul is a healthcare institution in Istanbul, Turkey that believes in the power of
technology and wants all complex systems in the hospital to work together in a smooth
coordination. It is a full-fledged hospital where international doctors and health workers from
various countries of the world, as well as academics from prestigious academic institutions
meet, and is one of the world's leading authorities in the field of health. The hospital has 1923
rooms with beds to be used for inpatients. There is a responsible doctor and a responsible
nurse specially appointed for each inpatient, and the patient's disease follow-up is constantly
recorded in the online environment. Outpatients come by making an online appointment which
is an appointment at a certain duration determined by the doctor with the help of artificial
intelligence technologies according to the condition of the disease, and the patient, so that no
incoming patient waits in line. Zospital Istanbul keeps the details of appointments, bills,
medicines and diseases in its database so that makes them easily processable. All these
facilitate the execution of hospital management systems in the light of technology.
# The Descriptions of Entities and Relationships in the ER Diagram:
* **Employees**: Employees stand for those who work in the hospital as a doctor or a nurse.
Therefore, there is an IS-A hierarchy among doctors, nurses and employees. The employee ID
is a unique primary key; some details about the employee such as name, e-mail address, home
address, phone number, and salary are stored among other attributes of this entity.

* **Doctors**: Doctors are the type of employees who work in Zospital Istanbul. They get
appointments from the system which are requested by the patient and given after their approval.
Consequently, they have a "Gets" relationship with “Appointments”. In addition, doctors are
assigned to inpatients to check their status. As a result, they have an "Assigned_D" relationship
with “Inpatients” with whom they are responsible, this relationship also stores the duration of the
assignment. Lastly, “Doctors” table stores two attributes that are the title and the department of
the doctor, different from nurses.

* **Nurses**: Nurses are the type of employees who work in Zospital Istanbul. Due to their work,
they are assigned to inpatients to take care of their needs according to the doctor’s instructions.
Therefore, they have an attribute storing the amount of patients they are responsible for
(pCount) which is an attribute different from doctors. Also, they have an "Assigned_N"
relationship with the “Inpatients” they are responsible for, this relationship stores the duration of
the assignment as well.

* **Patients**: Patients are people who come to Zospital Istanbul for a treatment, they are the main
entity of the database with a unique patient id. “Patients” table keeps the general details of the
patient such as name, age, height, weight, blood type, phone number and home address. It has
an IS-A hierarchy with the “Inpatients” table which is used to store the details for the inpatients,
and the “Outpatients” table which contains the operations about outpatients. It also has three
relationships: One of them is the “Has” relationship with the “Diseases” table which stores the
duration of the disease and the details of the diseases. Another one is the “Pays” relationship
with the “Bills” table which saves the payment type and date in addition to the details of the bill.
Lastly, it has a relationship “Takes” with the “Medicine” table which keeps the dose, amount and
expiration date of the medicine with the other details of the medicine.

* **Outpatient**: Outpatient is a type of patient who does not stay in a Zospital room. “Outpatients”
table has a "Makes" relationship with the “Appointments” table, it stores the appointments made
by outpatients under the approval of doctors. In addition to all the attributes that come from the
patient, the table has an attribute storing the number of times the patient visits the ZI.

* **Appointments**: It stores patients' appointments and allows doctors to get and approve them.
Therefore, it has a "Gets" relationship with the “Doctors” table, and also has a "Makes"
relationship with “Outpatients” table. The unique ID of the appointment is stored as a primary
key, the table saves the duration, start and end times of the appointments with their dates.
Additionally, it has the price of the appointment, and the approval status of the appointment.

* **Inpatient**: Inpatient is a type of patient who stays in a Zospital room. “Inpatients” table has an
"Assigned_D" relationship with the “Doctors” table, and an "Assigned_N" relationship with the
“Nurses” table; these are responsible employees from inpatients. In addition to all attributes
coming from the patient, it also keeps the arrival and leaving dates of the inpatient.

* **Medicine**: It is a table to store all medicines used in the ZI’s system so that it consists of all
medicines that the doctors can give to the patients. In addition to the unique ID of the
medicines, their names and selling prices are stored. “Medicine” table has a relationship with
the “Patients” table used to keep specific details for a specific medicine given to a patient, it
stores the amount and the dose of the medicine, and also the expiration date of it.

* **Diseases**: It stores the details of the diseases with their unique disease codes. Each disease
has attributes to differentiate from one another such as name, risk of disease and the type of
disease. Also, it has a “Has” relationship with the “Patients” table storing patients’ diseases.

* **Bills**: It stores details of all bills used in the Zospital Istanbul with each bill having a unique ID.
The table stores the billing date, and the costs of services such as medicalCost, roomCost and
the otherCharges separately. Additionally, it has a “Pays” relationship with the “Patients” table
where the information about the payment type and date are stored.

* **Rooms**: In the Zospital Istanbul, there are 1923 rooms with beds; but when all types of rooms
are added together, the total number of rooms becomes 2663. “Rooms” entity stores all of these
rooms’ details, such as their block, floor and room numbers. It also stores the type of the room,
availability of the room, and the cost of the room (if applicable). Additionally, it has a “Stays_in”
relationship with the “Inpatients” table which is used to match the rooms with the inpatients to
easily follow them.

# The ER Diagram of Zospital Istanbul Database Project:
<img width="412" alt="er" src="https://user-images.githubusercontent.com/61918785/219535926-46034e68-eedc-4cc9-bb10-e03deb6440a2.png">

