> [!IMPORTANT]
> This is a—hopefully—temporary fork of the official Doxygen.
> 
> It provides the "Add "Godbolt" link for \snippet" feature.
> See this pull request: https://github.com/doxygen/doxygen/pull/12455
>
### From the updated  documentation:
 
` \snippet['{'option'}'] <file-name> ( block_id )`
...
The `option` can be:
- ...
- The `option` `*godbolt` can be used to show a link below the code to execute the file <file-name> on https://godbolt.org/.
   The configuration of that execution is controlled by the file with the name given as an option, e.g., `gcc_162_godbolt`, 
   which could look like this:
```
      {
        "sessions": [
          {
            "id": 1,
            "language": "c++",
            "source": "$$godbolt$$",
            "compilers": [],
            "executors": [
              {
                "compiler": {
                  "id": "g162",
                  "libs": [],
                  "options": "-std=c++20"
                }
              }
            ]
          }
        ]
      }
```   
   - `$$godbolt$$` is the placeholder where the snippet file is inserted.
   - Such a file is called the "Client State" of Godbolt. The simplest way to get such a "Client State" is to set up 
     the scene interactively and obtain a short link via "Share". This short link can then be easily transformed into JSON
     via https://godbolt.org/api/shortlinkinfo/ `last part of short link`. These files are found in the INPUT directories.

### Testcase 154_snippet_godbolt.cpp

### Debug Doxyfile_DebugGodbolt
For quick interactive start.
in /testing
output e.g.:  doxygen\out\build\x64-Debug\bin\debug-output\html
makes: 
<img width="822" height="611" alt="image" src="https://github.com/user-attachments/assets/7ddbeb15-53ea-41f0-846e-a3b7204be19a" />
Click:
<img width="710" height="547" alt="image" src="https://github.com/user-attachments/assets/5315ff83-f0ea-4f5e-9ac4-837d1fabc99e" />


### In Real World:
https://www.alexweb.io/anyxx/talk_meeting_cpp26_samples_v26.html
<img width="959" height="683" alt="image" src="https://github.com/user-attachments/assets/7cc84971-1a62-467a-8931-def6c436a675" />


