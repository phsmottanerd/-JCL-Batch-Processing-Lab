<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 120" width="100%">
  <rect width="100%" height="100%" fill="#050805" rx="10"/>
  <rect width="100%" height="100%" fill="none" stroke="#00FF66" stroke-width="2" rx="10"/>
  <style>
    .title { font-family: 'Courier New', monospace; font-weight: bold; fill: #00FF66; font-size: 28px; }
    .sub { font-family: 'Courier New', monospace; fill: #00CC55; font-size: 14px; letter-spacing: 3px; }
    @keyframes pulse { 0%, 100% { opacity: 0.3; } 50% { opacity: 0.9; } }
    .glow { animation: pulse 2s infinite; }
  </style>
  <text x="50%" y="45%" text-anchor="middle" class="title">JCL BATCH PROCESSING LAB</text>
  <text x="50%" y="75%" text-anchor="middle" class="sub glow">■ IBM z/OS MAINFRAME ENVIRONMENT ■</text>
</svg>
$$\color{#00FF66}{\textsf{Practical Mainframe laboratory focused on JCL batch processing in an IBM z/OS training environment.}}$$$$\color{#00FF66}{\textsf{The project demonstrates the complete learning workflow: writing JCL, submitting a batch job, receiving a JES job ID, and monitoring the job through SDSF.}}$$$$\color{#00FF66}{\textsf{MAINFRAME • JCL • BATCH • JES • SDSF • z/OS}}$$<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
  <rect width="100%" height="100%" fill="#050805" rx="5" stroke="#00FF66" stroke-width="1"/>
  <style>
    .sec { font-family: 'Courier New', monospace; font-weight: bold; fill: #00FF66; font-size: 18px; }
    @keyframes fade { 0%, 100% { opacity: 0.5; } 50% { opacity: 1; } }
    .anim { animation: fade 3s infinite ease-in-out; }
  </style>
  <text x="50%" y="60%" text-anchor="middle" class="sec anim">> 01 — PROJECT OVERVIEW <</text>
</svg>
$$\color{#00FF66}{\textsf{This repository documents a hands-on JCL Batch Processing Lab performed on an IBM z/OS environment.}}$$$$\color{#00FF66}{\textsf{The objective was not to create a large application, but to demonstrate the fundamental mechanics of a traditional Mainframe batch workflow using real z/OS tooling.}}$$$\color{#00FF66}{\textsf{Environment}}$$\color{#00FF66}{\textsf{Platform: IBM z/OS}}$$\color{#00FF66}{\textsf{Access environment: IBM training lab / Skytap}}$$\color{#00FF66}{\textsf{Interface: TSO / ISPF / IBM Personal Communications}}$$\color{#00FF66}{\textsf{Batch language: JCL}}$$\color{#00FF66}{\textsf{Job management: JES}}$$\color{#00FF66}{\textsf{Monitoring: SDSF}}$$\color{#00FF66}{\textsf{Utility used in the test: IEFBR14}}$<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
  <rect width="100%" height="100%" fill="#050805" rx="5" stroke="#00FF66" stroke-width="1"/>
  <style>
    .sec { font-family: 'Courier New', monospace; font-weight: bold; fill: #00FF66; font-size: 18px; }
    @keyframes fade { 0%, 100% { opacity: 0.5; } 50% { opacity: 1; } }
    .anim { animation: fade 3s infinite ease-in-out; }
  </style>
  <text x="50%" y="60%" text-anchor="middle" class="sec anim">> 02 — OBJECTIVES <</text>
</svg>
$$\color{#00FF66}{\textsf{The laboratory was designed to practice and demonstrate:}}$$$\color{#00FF66}{\textsf{JOB statement — job definition}}$$\color{#00FF66}{\textsf{EXEC statement — execution step}}$$\color{#00FF66}{\textsf{DD statement — data definition}}$$\color{#00FF66}{\textsf{SYSOUT=* — spool/output routing}}$$\color{#00FF66}{\textsf{JCL member creation in an ISPF library}}$$\color{#00FF66}{\textsf{Job submission from ISPF}}$$\color{#00FF66}{\textsf{JES job identification}}$$\color{#00FF66}{\textsf{Job monitoring through SDSF}}$$\color{#00FF66}{\textsf{Recognition of a JCL processing error}}$$$\color{#00FF66}{\textsf{This is intentionally a small, focused lab. Its value is the direct interaction with z/OS batch processing rather than the size of the code.}}$$<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
  <rect width="100%" height="100%" fill="#050805" rx="5" stroke="#00FF66" stroke-width="1"/>
  <style>
    .sec { font-family: 'Courier New', monospace; font-weight: bold; fill: #00FF66; font-size: 18px; }
    @keyframes fade { 0%, 100% { opacity: 0.5; } 50% { opacity: 1; } }
    .anim { animation: fade 3s infinite ease-in-out; }
  </style>
  <text x="50%" y="60%" text-anchor="middle" class="sec anim">> 03 — BATCH FLOW <</text>
</svg>
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
$$\color{#00FF66}{\textsf{The practical flow was: Create → Edit → Submit → Receive JOBID → Monitor → Analyze}}$$<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
  <rect width="100%" height="100%" fill="#050805" rx="5" stroke="#00FF66" stroke-width="1"/>
  <style>
    .sec { font-family: 'Courier New', monospace; font-weight: bold; fill: #00FF66; font-size: 18px; }
    @keyframes fade { 0%, 100% { opacity: 0.5; } 50% { opacity: 1; } }
    .anim { animation: fade 3s infinite ease-in-out; }
  </style>
  <text x="50%" y="60%" text-anchor="middle" class="sec anim">> 04 — JCL STRUCTURE <</text>
</svg>
$$\color{#00FF66}{\textsf{The laboratory member was: TSOXA86.ES52.EXEC(JCL01)}}$$+ //JCL01    JOB CLASS=A,MSGCLASS=X
+ //STEP01   EXEC PGM=IEFBR14
+ //SYSPRINT DD SYSOUT=*
+ //SYSOUT   DD SYSOUT=*
$\color{#00FF66}{\textsf{Line-by-line}}$StatementPurpose$\color{#00FF66}{\textsf{JOB}}$$\color{#00FF66}{\textsf{Defines the batch job}}$$\color{#00FF66}{\textsf{EXEC}}$$\color{#00FF66}{\textsf{Defines the program/step to execute}}$$\color{#00FF66}{\textsf{PGM=IEFBR14}}$$\color{#00FF66}{\textsf{Calls the IBM utility used for a simple execution test}}$$\color{#00FF66}{\textsf{DD}}$$\color{#00FF66}{\textsf{Defines data/output resources for the step}}$$\color{#00FF66}{\textsf{SYSOUT=*}}$$\color{#00FF66}{\textsf{Sends output to the JES spool}}$<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
  <rect width="100%" height="100%" fill="#050805" rx="5" stroke="#00FF66" stroke-width="1"/>
  <style>
    .sec { font-family: 'Courier New', monospace; font-weight: bold; fill: #00FF66; font-size: 18px; }
    @keyframes fade { 0%, 100% { opacity: 0.5; } 50% { opacity: 1; } }
    .anim { animation: fade 3s infinite ease-in-out; }
  </style>
  <text x="50%" y="60%" text-anchor="middle" class="sec anim">> 05 — EXECUTION & MONITORING <</text>
</svg>
$$\color{#00FF66}{\textsf{The job was submitted from the ISPF editor.}}$$+ JOB TSOXA861(JOB46704) SUBMITTED
$$\color{#00FF66}{\textsf{The job was then located through: SDSF ST}}$$+ TSOXA861  JOB46704
+ JOB46704 $HASP165 TSOXA861 ENDED AT ESSMVS1 - JCL ERROR CN(INTERNAL)
$$\color{#00FF66}{\textsf{This repository does not claim a successful batch completion.}}$$$$\color{#00FF66}{\textsf{The lab successfully demonstrated JCL creation, submission, JES job identification and SDSF monitoring, while the execution attempt exposed a JCL processing error. That distinction is intentional and documented accurately.}}$$<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
  <rect width="100%" height="100%" fill="#050805" rx="5" stroke="#00FF66" stroke-width="1"/>
  <style>
    .sec { font-family: 'Courier New', monospace; font-weight: bold; fill: #00FF66; font-size: 18px; }
    @keyframes fade { 0%, 100% { opacity: 0.5; } 50% { opacity: 1; } }
    .anim { animation: fade 3s infinite ease-in-out; }
  </style>
  <text x="50%" y="60%" text-anchor="middle" class="sec anim">> 06 — LAB EVIDENCE <</text>
</svg>
EvidenceDemonstrates$\color{#00FF66}{\textsf{IBM z/OS / TSO environment}}$$\color{#00FF66}{\textsf{Mainframe lab access}}$$\color{#00FF66}{\textsf{ISPF editor}}$$\color{#00FF66}{\textsf{JCL member creation}}$$\color{#00FF66}{\textsf{JCL01 source}}$$\color{#00FF66}{\textsf{JOB / EXEC / DD structure}}$$\color{#00FF66}{\textsf{Submission message}}$$\color{#00FF66}{\textsf{JES job creation}}$$\color{#00FF66}{\textsf{JOB46704}}$$\color{#00FF66}{\textsf{Job identification}}$$\color{#00FF66}{\textsf{SDSF Status Display}}$$\color{#00FF66}{\textsf{Job monitoring}}$$\color{#00FF66}{\textsf{JCL Error message}}$$\color{#00FF66}{\textsf{Error detection / troubleshooting}}$<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
  <rect width="100%" height="100%" fill="#050805" rx="5" stroke="#00FF66" stroke-width="1"/>
  <style>
    .sec { font-family: 'Courier New', monospace; font-weight: bold; fill: #00FF66; font-size: 18px; }
    @keyframes fade { 0%, 100% { opacity: 0.5; } 50% { opacity: 1; } }
    .anim { animation: fade 3s infinite ease-in-out; }
  </style>
  <text x="50%" y="60%" text-anchor="middle" class="sec anim">> 07 — WHAT THIS DEMONSTRATES TO RECRUITERS <</text>
</svg>
$$\color{#00FF66}{\textsf{This project is intentionally positioned as a hands-on Mainframe laboratory, not as a claim of production z/OS administration experience.}}$$$$\color{#00FF66}{\textsf{A recruiter reviewing this repository can quickly identify practical exposure to:}}$$$\color{#00FF66}{\textsf{IBM z/OS}}$$\color{#00FF66}{\textsf{JCL}}$$\color{#00FF66}{\textsf{Batch processing concepts}}$$\color{#00FF66}{\textsf{JOB / EXEC / DD}}$$\color{#00FF66}{\textsf{JES job submission}}$$\color{#00FF66}{\textsf{SDSF monitoring}}$$\color{#00FF66}{\textsf{ISPF}}$$\color{#00FF66}{\textsf{Mainframe troubleshooting}}$<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
  <rect width="100%" height="100%" fill="#050805" rx="5" stroke="#00FF66" stroke-width="1"/>
  <style>
    .sec { font-family: 'Courier New', monospace; font-weight: bold; fill: #00FF66; font-size: 18px; }
    @keyframes fade { 0%, 100% { opacity: 0.5; } 50% { opacity: 1; } }
    .anim { animation: fade 3s infinite ease-in-out; }
  </style>
  <text x="50%" y="60%" text-anchor="middle" class="sec anim">> 08 — NEXT STEPS <</text>
</svg>
+ [ ] Correct and re-submit the JCL
+ [ ] Obtain a successful completion / return code
+ [ ] Add dataset allocation with DISP
+ [ ] Add a real input/output dataset
+ [ ] Expand the job to multiple EXEC steps
+ [ ] Document JES output in detail
+ [ ] Add additional SDSF evidence
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
  <rect width="100%" height="100%" fill="#050805" rx="5" stroke="#00FF66" stroke-width="1"/>
  <style>
    .sec { font-family: 'Courier New', monospace; font-weight: bold; fill: #00FF66; font-size: 18px; }
    @keyframes fade { 0%, 100% { opacity: 0.5; } 50% { opacity: 1; } }
    .anim { animation: fade 3s infinite ease-in-out; }
  </style>
  <text x="50%" y="60%" text-anchor="middle" class="sec anim">> 09 — REPOSITORY STRUCTURE <</text>
</svg>
+ jcl-batch-processing-lab/
+ │
+ ├── README.md
+ ├── jcl/
+ │   └── JCL01.jcl
+ ├── docs/
+ │   └── projeto.md
+ ├── screenshots/
+ │   ├── 01-zos-environment.png
+ │   ├── 02-jcl-editor.png
+ │   ├── 03-job-submitted.png
+ │   ├── 04-sdsf-status.png
+ │   └── 05-jcl-error.png
+ └── assets/
+     ├── 01-title.svg
+     ├── 02-overview.svg
+     ├── 03-objectives.svg
+     ├── 04-architecture.svg
+     ├── 05-jcl.svg
+     ├── 06-execution.svg
+     ├── 07-evidence.svg
+     ├── 08-recruiters.svg
+     └── 09-future.svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
  <rect width="100%" height="100%" fill="#050805" rx="5" stroke="#00FF66" stroke-width="1"/>
  <style>
    .sec { font-family: 'Courier New', monospace; font-weight: bold; fill: #00FF66; font-size: 18px; }
    @keyframes fade { 0%, 100% { opacity: 0.5; } 50% { opacity: 1; } }
    .anim { animation: fade 3s infinite ease-in-out; }
  </style>
  <text x="50%" y="60%" text-anchor="middle" class="sec anim">> 10 — AUTHOR <</text>
</svg>
$$\color{#00FF66}{\textsf{Paulo Henrique Santana Motta}}$$$$\color{#00FF66}{\textsf{Mainframe • COBOL • Linux • JCL • Automation • Cybersecurity}}$$$$\color{#00FF66}{\textsf{Building practical projects that connect legacy systems, Mainframe technologies, Linux, automation and modern development.}}$$+ ╔══════════════════════════════════════════════════════════╗
+ ║  IBM z/OS  |  JCL  |  JES  |  SDSF  |  BATCH PROCESSING ║
+ ╚══════════════════════════════════════════════════════════╝
$$\color{#00FF66}{\textsf{END OF LAB}}$$
