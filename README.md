<div align="center">
  <img src="assets/01-title.svg" alt="JCL Batch Processing Lab" width="100%">
</div>

```diff
+ Practical Mainframe laboratory focused on JCL batch processing in an IBM z/OS training environment.
+ The project demonstrates the complete learning workflow: writing JCL, submitting a batch job, receiving a JES job ID, and monitoring the job through SDSF.
+ 
+ MAINFRAME • JCL • BATCH • JES • SDSF • z/OS

+ 01 — PROJECT OVERVIEW
+ 
+ This repository documents a hands-on JCL Batch Processing Lab performed on an IBM z/OS environment.
+ The objective was not to create a large application, but to demonstrate the fundamental mechanics of a traditional Mainframe batch workflow using real z/OS tooling.
+ 
+ Environment:
+ - Platform: IBM z/OS
+ - Access environment: IBM training lab / Skytap
+ - Interface: TSO / ISPF / IBM Personal Communications
+ - Batch language: JCL
+ - Job management: JES
+ - Monitoring: SDSF
+ - Utility used in the test: IEFBR14

+ 02 — OBJECTIVES
+ 
+ The laboratory was designed to practice and demonstrate:
+ - JOB statement — job definition
+ - EXEC statement — execution step
+ - DD statement — data definition
+ - SYSOUT=* — spool/output routing
+ - JCL member creation in an ISPF library
+ - Job submission from ISPF
+ - JES job identification
+ - Job monitoring through SDSF
+ - Recognition of a JCL processing error
+ 
+ This is intentionally a small, focused lab. Its value is the direct interaction with z/OS batch processing rather than the size of the code.

+ 03 — BATCH FLOW
+ 
+ ┌──────────────────┐
+ │      JCL01       │
+ │     ISPF Edit    │
+ └────────┬─────────┘
+          │ SUBMIT
+          ▼
+ ┌──────────────────┐
+ │       JES        │
+ │  Job processing  │
+ └────────┬─────────┘
+          │
+          ▼
+ ┌──────────────────┐
+ │      SDSF        │
+ │ Status / Output  │
+ └──────────────────┘
+ 
+ The practical flow was: Create → Edit → Submit → Receive JOBID → Monitor → Analyze

+ 04 — JCL STRUCTURE
+ 
+ The laboratory member was: TSOXA86.ES52.EXEC(JCL01)
+ 
+ //JCL01    JOB CLASS=A,MSGCLASS=X
+ //STEP01   EXEC PGM=IEFBR14
+ //SYSPRINT DD SYSOUT=*
+ //SYSOUT   DD SYSOUT=*
+ 
+ Line-by-line:
+ - JOB: Defines the batch job
+ - EXEC: Defines the program/step to execute
+ - PGM=IEFBR14: Calls the IBM utility used for a simple execution test
+ - DD: Defines data/output resources for the step
+ - SYSOUT=*: Sends output to the JES spool
+ 04 — JCL STRUCTURE
+ 
+ The laboratory member was: TSOXA86.ES52.EXEC(JCL01)
+ 
+ //JCL01    JOB CLASS=A,MSGCLASS=X
+ //STEP01   EXEC PGM=IEFBR14
+ //SYSPRINT DD SYSOUT=*
+ //SYSOUT   DD SYSOUT=*
+ 
+ Line-by-line:
+ - JOB: Defines the batch job
+ - EXEC: Defines the program/step to execute
+ - PGM=IEFBR14: Calls the IBM utility used for a simple execution test
+ - DD: Defines data/output resources for the step
+ - SYSOUT=*: Sends output to the JES spool

+ 05 — EXECUTION & MONITORING
+ 
+ The job was submitted from the ISPF editor.
+ 
+ JOB TSOXA861(JOB46704) SUBMITTED
+ 
+ The job was then located through: SDSF ST
+ 
+ TSOXA861  JOB46704
+ JOB46704 $HASP165 TSOXA861 ENDED AT ESSMVS1 - JCL ERROR CN(INTERNAL)
+ 
+ Important:
+ This repository does not claim a successful batch completion.
+ The lab successfully demonstrated JCL creation, submission, JES job identification and SDSF monitoring, while the execution attempt exposed a JCL processing error. That distinction is intentional and documented accurately.

+ 06 — LAB EVIDENCE
+ 
+ Evidence & Demonstrates:
+ - IBM z/OS / TSO environment: Mainframe lab access
+ - ISPF editor: JCL member creation
+ - JCL01 source: JOB / EXEC / DD structure
+ - Submission message: JES job creation
+ - JOB46704: Job identification
+ - SDSF Status Display: Job monitoring
+ - JCL Error message: Error detection / troubleshooting

+ 07 — WHAT THIS DEMONSTRATES TO RECRUITERS
+ 
+ This project is intentionally positioned as a hands-on Mainframe laboratory, not as a claim of production z/OS administration experience.
+ A recruiter reviewing this repository can quickly identify practical exposure to:
+ - IBM z/OS
+ - JCL
+ - Batch processing concepts
+ - JOB / EXEC / DD
+ - JES job submission
+ - SDSF monitoring
+ - ISPF
+ - Mainframe troubleshooting
