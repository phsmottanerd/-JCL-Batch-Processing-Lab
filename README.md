[readme_reeditado.md](https://github.com/user-attachments/files/33186723/readme_reeditado.md)

Practical Mainframe laboratory focused on JCL batch processing in an IBM z/OS training environment.


The project demonstrates the complete learning workflow: writing JCL, submitting a batch job, receiving a JES job ID, and monitoring the job through SDSF.

MAINFRAME • JCL • BATCH • JES • SDSF • z/OS

This repository documents a hands-on JCL Batch Processing Lab performed on an IBM z/OS environment.

The objective was not to create a large application, but to demonstrate the fundamental mechanics of a traditional Mainframe batch workflow using real z/OS tooling.

### Environment

* Platform: IBM z/OS

* Access environment: IBM training lab / Skytap

* Interface: TSO / ISPF / IBM Personal Communications

* Batch language: JCL

* Job management: JES

* Monitoring: SDSF

* Utility used in the test: IEFBR14

The laboratory was designed to practice and demonstrate:

* JOB statement — job definition

* EXEC statement — execution step

* DD statement — data definition

* SYSOUT=\* — spool/output routing

* JCL member creation in an ISPF library

* Job submission from ISPF

* JES job identification

* Job monitoring through SDSF

* Recognition of a JCL processing error

This is intentionally a small, focused lab. Its value is the direct interaction with z/OS batch processing rather than the size of the code.

```
┌──────────────────┐
│      JCL01       │
│     ISPF Edit    │
└────────┬─────────┘
         │ SUBMIT
         ▼
┌──────────────────┐
│       JES        │
│  Job processing  │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│      SDSF        │
│ Status / Output  │
└──────────────────┘

```

The practical flow was:

Create → Edit → Submit → Receive JOBID → Monitor → Analyze

The laboratory member was:

```
TSOXA86.ES52.EXEC(JCL01)

```

The JCL used for the first execution attempt was:

```
//JCL01    JOB CLASS=A,MSGCLASS=X
//STEP01   EXEC PGM=IEFBR14
//SYSPRINT DD SYSOUT=*
//SYSOUT   DD SYSOUT=*

```

### Line-by-line

| 

| **Statement** | **Purpose** | 
| JOB | Defines the batch job | 
| EXEC | Defines the program/step to execute | 
| PGM=IEFBR14 | Calls the IBM utility used for a simple execution test | 
| DD | Defines data/output resources for the step | 
| SYSOUT=\* | Sends output to the JES spool | 

The job was submitted from the ISPF editor.

The z/OS environment generated:

```
JOB TSOXA861(JOB46704) SUBMITTED

```

The job was then located through:

```
SDSF ST

```

The status display showed:

```
TSOXA861  JOB46704

```

The job subsequently ended with:

```
JOB46704 $HASP165 TSOXA861 ENDED AT ESSMVS1 - JCL ERROR CN(INTERNAL)

```

### Important

This repository does not claim a successful batch completion.

The lab successfully demonstrated JCL creation, submission, JES job identification and SDSF monitoring, while the execution attempt exposed a JCL processing error. That distinction is intentional and documented accurately.

For a portfolio project, this is preferable to presenting an unverified MAXCC=0000 as if it had occurred.

Suggested evidence captured during the laboratory:

| **Evidence** | **Demonstrates** | 
| IBM z/OS / TSO environment | Mainframe lab access | 
| ISPF editor | JCL member creation | 
| JCL01 source | JOB / EXEC / DD structure | 
| Submission message | JES job creation | 
| JOB46704 | Job identification | 
| SDSF Status Display | Job monitoring | 
| JCL Error message | Error detection / troubleshooting | 

> Screenshots can be placed in screenshots/ and linked here as the repository evidence is organized.

This project is intentionally positioned as a hands-on Mainframe laboratory, not as a claim of production z/OS administration experience.

A recruiter reviewing this repository can quickly identify practical exposure to:

* IBM z/OS

* JCL

* Batch processing concepts

* JOB / EXEC / DD

* JES job submission

* SDSF monitoring

* ISPF

* Mainframe troubleshooting

* Understanding of the relationship between JCL, JES and batch execution

### Professional positioning

> Hands-on laboratory experience with JCL batch processing in IBM z/OS, including ISPF editing, job submission, JES job identification and SDSF monitoring.

This wording keeps the project technically relevant while remaining faithful to what was actually performed.

Possible future iterations:

```
[ ] Correct and re-submit the JCL
[ ] Obtain a successful completion / return code
[ ] Add dataset allocation with DISP
[ ] Add a real input/output dataset
[ ] Expand the job to multiple EXEC steps
[ ] Document JES output in detail
[ ] Add additional SDSF evidence

```

```
jcl-batch-processing-lab/
│
├── README.md
├── jcl/
│   └── JCL01.jcl
├── docs/
│   └── projeto.md
├── screenshots/
│   ├── 01-zos-environment.png
│   ├── 02-jcl-editor.png
│   ├── 03-job-submitted.png
│   ├── 04-sdsf-status.png
│   └── 05-jcl-error.png
└── assets/
    ├── 01-title.svg
    ├── 02-overview.svg
    ├── 03-objectives.svg
    ├── 04-architecture.svg
    ├── 05-jcl.svg
    ├── 06-execution.svg
    ├── 07-evidence.svg
    ├── 08-recruiters.svg
    └── 09-future.svg

```

Paulo Henrique Santana Motta


Mainframe • COBOL • Linux • JCL • Automation • Cybersecurity

> Building practical projects that connect legacy systems, Mainframe technologies, Linux, automation and modern development.

```
╔══════════════════════════════════════════════════════════╗
║  IBM z/OS  |  JCL  |  JES  |  SDSF  |  BATCH PROCESSING ║
╚══════════════════════════════════════════════════════════╝

```

END OF LAB

Prontinho! É só copiar o código do bloco acima e colar direto no arquivo `README.md` do seu repositório no GitHub.
