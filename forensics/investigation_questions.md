# 🔍 Investigation Questions
## Operation: Cipherlock — Forensics Analysis

Answer each question in a new file: `forensics/my_answers.md`  
Use evidence from `server_log.txt`, `email_header.txt`, and `file_metadata.txt` to support every answer.

---

### Section A — Server Log Analysis

**Q1.** What is the username of the primary suspect? What evidence from the server log supports this?
jdoe, he is the most active
**Q2.** At what time did the suspect's activity become suspicious? What specifically changed between their daytime and nighttime sessions? (Look at IP addresses AND files accessed.)
23:47, they went from doing quarterly reports to gathering everything
**Q3.** List every file the suspect downloaded during the suspicious session. Why would each of these files be considered sensitive or confidential?
client data, financial master, ssn database. all of these are sensitive and confidential
**Q4.** One of the entries in the server log shows a POST request to `/admin/export.php`. What does a POST request mean, and why is this action more concerning than a GET request in this context?
the suspect is exporting the data to a flash drive
---

### Section B — Email Header Analysis

**Q5.** What is the originating IP address of the email? How does this connect to the server log?
10.45.88.201
**Q6.** Why is the use of ProtonMail significant in this investigation? What does it suggest about the suspect's intent?
proton mail is used for anonymous mailing, it helps hide who you are.
**Q7.** The email subject line is blank. Why might a suspect deliberately send an email with no subject? What technique might they be using?
to hide intent, or to stand out to the reader.
**Q8.** Compare the email timestamp to the server log. What does the timeline suggest about the order of events on the night of April 18?
he was emailed then he did what we see on the log.
---

### Section C — File Metadata Analysis

**Q9.** The three large data files (`.zip`, `.xlsx`, `.csv`) all have the same "Created" date and time range. What does this tell you about how they got onto the USB drive?
they were copied.
**Q10.** The "Last Accessed" timestamp on every file is `2026-04-19 08:15:01`. Why are they all identical? What event caused this?
they were open at the same time
**Q11.** `note_to_self.txt` was created at `23:44:00` and the email was sent at `23:32:00`. Does this timeline make sense given what the note contains? Explain.
yes, he could have already had this planned out and then did that.
---

### Section D — Putting It All Together

**Q12.** Write a 1–2 paragraph **incident summary** describing what you believe happened on the night of April 18, 2026. Use specific evidence (timestamps, filenames, IP addresses) to support your conclusion. This is similar to what a real digital forensics analyst would write in an official report.
jdoe does his work at 12:00. then jdoe sends the email at 23:32 implying that the other person may have been nearby. jdoe grabs said files and puts them on a drive. then logs out at 23:52 and meets the other person at midnight.
**Q13.** What laws or regulations might the suspect have violated? Name at least TWO (examples: CFAA — Computer Fraud and Abuse Act, HIPAA, FERPA, state data breach laws).
CFAA and HIPPA
**Q14.** If you were the IT security team, what THREE security measures could have prevented or detected this breach earlier?
monitor emails, limit access, and review current security.