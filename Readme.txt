Tema 3 LFA FloreaAdrian336CB
============================
		Regex parser

Detalii implementare:

main.py:
	- luam input-ul din fisier si il parsam un pic pentru a scoate
		kleene star-uri in plus
	- cream un obiect NFAfromRegex, dupa care il afisam dupa prelucrare
	- am hardcodat un singur fisier de output pentru NFA-DFA, pentru ca
		checkerul se strica altfel

Workspace.py:

	class Automata:
		- clasa definita pentru a reprezenta automatul nedeterminist,
			fiecare metoda fiind folosita pentru a adauga intrari in dictionar
			sau in setul de stari
		- metodele newBuildFromNumber si newBuildFromEquivalentStates creaza
			o noua instanta de Automata in functie de instanta principala
			( sunt apelate cand construim bucatile de automat )

	class BuildAutomata:
		- clasa definita pentru a construi tranzitii pe cazuri:
			> cazul de baza
			> operatorul <|>
			> concatenare
			> kleene star

	class NFAfromRegex:
		- clasa definita pentru a parsa expresia regulata si pentru
			a crea tranzitiile pentru automatul nedeterminist
		- se folosesc operatii de stack pentru a ordona cum
			trebuie operatiile, dupa care se contruieste pe bucati
			automatul in functie de operatorul intalnit (metoda 
			processOperator)