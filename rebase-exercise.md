Zuerst erstellen wir ein neues repository mit git init und wechseln in das Verzeichnis:
```` bash

git init rebase-exercise
cd rebase-exercise
````

Dann erstellen wir eine Datei namens onMain.md mit touch.
```` bash

touch onMain.md
````

Als nächstes erstellen wir einen neuen branch namens A-feature mit
```` bash

git checkout -b A-feature.
````
Wir erstellen eine Datei namens onBranch.md errneud mit touch und commiten die Änderung:

```` bash

git add onBranch.md
git commit -m "Add onBranch.md in A-feature branch"

````

Wir ändern die datei onBranch.md und commiten die Änderung erneut:

```` bash

echo "Some changes in A-feature branch"
git add onBranch.md
git commit -m "Update onBranch.md in A-feature branch"
````
Wir schauen die historie mit git log an, um die commits zu sehen.
```` 
Author: MatDara <matyas.darabos@htl-leonding.ac.at>
Date:   Wed Dec 3 12:35:37 2025 +0100

    added some lines onBranch.md

commit 1a66367643eb888e47b58cc75bdb33babcec20e7 (origin/main, origin/HEAD)
Author: MatDara <matyas.darabos@htl-leonding.ac.at>
Date:   Wed Dec 3 12:33:52 2025 +0100

    added onBranch.md

commit c4ce02b9821538fda27b09a3beb168b09777ecf2 (main)
Author: MatDara <m.darabos@students.htl-leonding.ac.at>
Date:   Wed Dec 3 12:14:09 2025 +0100

    Create onMain.md

commit 21549f3577199a5e17c82a94d37ee74332bda34d
Author: MatDara <m.darabos@students.htl-leonding.ac.at>
Date:   Wed Dec 3 12:13:15 2025 +0100

    Initial commit
````

wir wechseln zurück zum main branch und schauen und die historie an:

````
commit c4ce02b9821538fda27b09a3beb168b09777ecf2 (HEAD, main)
Author: MatDara <m.darabos@students.htl-leonding.ac.at>
Date:   Wed Dec 3 12:14:09 2025 +0100

    Create onMain.md

commit 21549f3577199a5e17c82a94d37ee74332bda34d
Author: MatDara <m.darabos@students.htl-leonding.ac.at>
Date:   Wed Dec 3 12:13:15 2025 +0100

    Initial commit
````
Uns fällt auf, dass der main branch hinter dem A-feature branch zurückliegt.

Wir ändern die datei onMain.md und commiten die Änderung:

````
echo "Some changes in main branch"
git add onMain.md
git commit -m "Added some lines onMain.md"
````
wir wiederholen den schritt und ändern die datei onMain.md erneut und commiten die änderung

Wir schauen uns die historie an:

````
commit 975318def7069060a84a5907af10e37bb4b9cab6 (HEAD -> Main)
Author: MatDara <matyas.darabos@htl-leonding.ac.at>
Date:   Wed Dec 3 12:46:00 2025 +0100

    added another line in onMain.md


commit 557f333a3e09ee58eb2753febbcab943df9c3b1d
Author: MatDara <matyas.darabos@htl-leonding.ac.at>
Date:   Wed Dec 3 12:45:23 2025 +0100

    add even more lines in onMain.md

commit 44261667976c9e40410811c3e7a913ccd849ac8e
Author: MatDara <matyas.darabos@htl-leonding.ac.at>
Date:   Wed Dec 3 12:45:06 2025 +0100

    add even more lines in onMain.md

commit 5b809da35e8dd1acf0c90558cb7b733bb41a4dd8
Author: MatDara <matyas.darabos@htl-leonding.ac.at>
Date:   Wed Dec 3 12:44:31 2025 +0100

    add some lines in onMain.md

commit c4ce02b9821538fda27b09a3beb168b09777ecf2
Author: MatDara <m.darabos@students.htl-leonding.ac.at>
Date:   Wed Dec 3 12:14:09 2025 +0100

    Create onMain.md

commit 21549f3577199a5e17c82a94d37ee74332bda34d
Author: MatDara <m.darabos@students.htl-leonding.ac.at>
Date:   Wed Dec 3 12:13:15 2025 +0100

    Initial commit
(END)
````
wir gehen wieder in den A-feature branch mit git checkout A-feature und führen ein merge auf den main branch durch mit git merge main

```` bash
git checkout A-feature
git merge main
````
wir schauen uns die historie an:

````


