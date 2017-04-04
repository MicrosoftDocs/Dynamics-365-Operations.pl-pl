---
title: "Użyj dodatku programu Excel"
description: "W tym temacie wyjaśniono, jak otworzyć dane jednostki w programie Microsoft Excel i następnie wyświetlać, aktualizacji i edytować dane przy użyciu dodatek Microsoft Dynamics Office dla programu Excel. Aby otworzyć dane jednostki, można uruchomić z programu Excel albo Microsoft Dynamics 365 dla operacji."
author: ChrisGarty
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 267914
ms.assetid: 4e6c7194-a059-4057-bd62-ec0c802c36fd
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: af7e7288f741b3c519227e2778c4c4311c3a2012
ms.openlocfilehash: 8af663b47117759ed3b2e2ed8eee85ae4df100d1
ms.lasthandoff: 03/31/2017


---

# <a name="use-the-excel-add-in"></a>Użyj dodatku programu Excel

W tym temacie wyjaśniono, jak otworzyć dane jednostki w programie Microsoft Excel i następnie wyświetlać, aktualizacji i edytować dane przy użyciu dodatek Microsoft Dynamics Office dla programu Excel. Aby otworzyć dane jednostki, można uruchomić z programu Excel albo Microsoft Dynamics 365 dla operacji.

Otwierając dane jednostki w programie Microsoft Excel, można szybko i łatwo umożliwia wyświetlanie i edytowanie danych przy użyciu dodatek Microsoft Dynamics Office dla programu Excel. Ten dodatek wymaga programu Microsoft Excel 2016. **Uwaga:** Jeśli dzierżawcy Microsoft Azure usługi Active Directory (Azure AD) jest skonfigurowany do używania programu Active Directory Federation Services (AD FS), należy się upewnić, że maja 2016 aktualizacja została zainstalowana, tak, że dodatek programu Excel można poprawnie zalogowanie.

## <a name="open-entity-data-in-excel-when-you-start-from-dynamics-365-for-operations"></a>Otwórz w programie Excel dane jednostki, po ponownym uruchomieniu z 365 Dynamics dla operacji
1.  Na stronie usługi Microsoft Dynamics 365 dla operacji, kliknij przycisk **Otwórz w programie Microsoft Office**. Jeśli główne źródło danych (tabeli) na stronie jest taka sama jak głównego źródła danych dla jakimikolwiek jednostkami, domyślnie **otwarty w programie Excel** opcje są generowane dla strony. **Otwórz w programie Excel** opcje można znaleźć na stronach często używanych, takich jak **wszystkich dostawców** i **wszystkich klientów**.
2.  Kliknij **Otwórz w programie Excel** opcji, a następnie otwórz skoroszyt, który jest generowany. Ten skoroszyt zawiera informacje wiązania dla podmiotu, wskaźnik do środowiska i wskaźnik do dodatek programu Excel.
3.  W programie Excel, kliknij przycisk **włączyć edycję** Aby włączyć dodatek programu Excel do uruchomienia. Dodatek programu Excel jest uruchamiany w okienku po prawej stronie okna programu Excel.
4.  Jeśli korzystasz z dodatek programu Excel po raz pierwszy, kliknij przycisk **zaufanie to**.
5.  Jeśli zostanie wyświetlony monit logowania, kliknij przycisk **logowania**, a następnie zaloguj się przy użyciu tych samych poświadczeń używanych do logowania do systemu Dynamics 365 dla operacji. Dodatek programu Excel będzie używać poprzedniego kontekstu logowanie w programie Internet Explorer i automatyczne logowanie, jeżeli jest to możliwe. W związku z tym Sprawdź nazwę użytkownika w prawym górnym rogu dodatek programu Excel.

Dodatek programu Excel automatycznie odczytuje dane dla wybranego obiektu. Należy zauważyć, że nie będzie żadnych danych w skoroszycie do dodatek programu Excel odczytuje go.

## <a name="open-entity-data-in-excel-when-you-start-from-excel"></a>Otwórz w programie Excel dane jednostki, podczas uruchamiania programu Excel
1.  W programie Excel na **Wstaw** kartę w **dodatki** grupy, kliknij przycisk **sklep** otworzyć magazynu pakietu Office.
2.  W sklepie Office, wyszukaj słowo kluczowe "Dynamics", a następnie kliknij przycisk **Dodaj** obok **dodatek Microsoft Dynamics Office** (dodatek programu Excel).
3.  Jeśli korzystasz z dodatek programu Excel po raz pierwszy, kliknij przycisk **zaufanie to** Aby włączyć dodatek programu Excel do uruchomienia. Dodatek programu Excel jest uruchamiany w okienku po prawej stronie okna programu Excel.
4.  Kliknij **dodać informacje o serwerze** otworzyć **opcje** okienka.
5.  Kopiuj adres URL przeglądarki od celu Dynamics 365 dla wystąpienia operacji, wklej go do **adres URL serwera** w polu, a następnie Usuń wszystko po nazwie hosta (na przykład usunąć **/? cmp = usmf & mi = CustTableListPage**). Wynikowego adresu URL powinna mieć tylko nazwa hosta (na przykład **https://xxx.dynamics.com**).
6.  Kliknij **OK**, a następnie kliknij przycisk **tak** o potwierdzenie zmiany. Program Excel dodać zostanie ponownie uruchomiony i ładuje metadane. **Projekt** przycisk jest teraz dostępny. Jeśli dodatek programu Excel ma **załadować apletów** przycisk, prawdopodobnie nie jesteś zalogowany jako poprawny użytkownik. Aby uzyskać więcej informacji zobacz "przycisk aplety obciążenia jest widoczny" w sekcji "Rozwiązywanie problemów" w tym temacie.
7.  Kliknij **projekt**. Dodatek programu Excel pobiera metadanych jednostki.
8.  Kliknij **Dodaj tabelę**. Zostanie wyświetlona lista elementów. Podmioty są wymienione w formacie "Nazwa – Label".
9.  Umożliwia wybranie jednostki na liście, takie jak **odbiorca — klienci**, a następnie kliknij przycisk **dalej**.
10. Aby dodać pole z **dostępne pola** na liście, aby **wybrane pola** listy, kliknij pole, a następnie kliknij **Dodaj**. Alternatywnie kliknij dwukrotnie pole.
11. Po dodaniu żądanego pola, aby **wybrane pola** listy, upewnij się, że kursor znajduje się w odpowiednim miejscu w arkuszu (na przykład komórka A1), a następnie kliknij **Sporządzono**. Następnie kliknij przycisk **Sporządzono** aby zakończyć projektanta.
12. Kliknij **Odśwież** do ciągnięcia w zestawie danych.

## <a name="view-and-update-entity-data-in-excel"></a>Przeglądanie i aktualizowanie jednostki danych w programie Excel
Po dodatek Excel odczytuje dane jednostki do skoroszytu, można aktualizować dane w dowolnym momencie, klikając **Odśwież** w dodatek programu Excel.

## <a name="edit-entity-data-in-excel"></a>Edycja jednostki danych w programie Excel
Można zmienić dane jednostki, jako wymagane, a następnie opublikować ją przywrócić, klikając **Opublikuj** w dodatek programu Excel. Aby edytować rejestr, zaznacz komórki w arkuszu, a następnie zmień wartość komórki. Aby dodać nowy rekord, wykonaj jedną z następujących czynności:

-   Kliknij w dowolnym miejscu arkusza, a następnie kliknij przycisk **nowy** w dodatek programu Excel.
-   Kliknij w ostatnim wierszu arkusza, a następnie naciśnij klawisz Tab, aż kursor znajdzie się poza ostatniej kolumnie tego wiersza i tworzony jest nowy wiersz.
-   Kliknij w wierszu bezpośrednio poniżej arkusza i zacząć wprowadzać dane w komórce. Po przeniesieniu fokusu poza tę komórkę arkusza rozszerza się nowy wiersz.

Aby usunąć rekord, należy wykonać jedną z następujących czynności:

-   Kliknij prawym przyciskiem myszy numer wiersza obok wiersza arkusza do usunięcia, a następnie kliknij przycisk **usunąć**.
-   Kliknij prawym przyciskiem myszy w wierszu arkusza, aby usunąć, a następnie kliknij przycisk **usunąć**&gt;**wierszy tabeli**.

## <a name="add-or-remove-columns"></a>Dodaj lub usuń kolumny
Aby dopasować kolumny, które są automatycznie dodawane do arkusza może używać projektanta.

1.  Uruchom danych źródłowych projektant dodatek programu Excel klikając **opcje** (symbol koła zębatego), a następnie wybierając **włączyć projekt** pole wyboru.
2.  Kliknij **projekt** w dodatek programu Excel. Wymienione są wszystkie źródła danych.
3.  Obok źródła danych, kliknij przycisk **edytować** przycisk (symbol ołówka).
4.  Skorygować listę w **wybrane pola** jak potrzebujesz listy:
    -   Aby dodać pole z **dostępne pola** na liście, aby **wybrane pola** listy, kliknij pole, a następnie kliknij **Dodaj**. Alternatywnie kliknij dwukrotnie pole.
    -   Aby usunąć pole z **wybrane pola** listy, kliknij pole, a następnie kliknij **usunąć**. Alternatywnie kliknij dwukrotnie pole.
    -   Aby zmienić kolejność pól, kliknij pole w **wybrane pola** listy, a następnie kliknij **się** lub **w dół**.

5.  Zastosuj zmiany do źródła danych poprzez kliknięcie **aktualizacja**. Następnie kliknij przycisk **Sporządzono** aby zakończyć projektanta. Jeśli dodano pola (kolumny), kliknij przycisk **Odśwież** do ciągnięcia w zaktualizowany zbiór danych.

## <a name="httpspowerappsmicrosoftcomenustutorialsdataplatforminteractiveexceltroubleshootingtroubleshooting"></a>[](https://powerapps.microsoft.com/enus/tutorials/dataplatforminteractiveexcel/#troubleshooting)Troubleshooting
Istnieje kilka problemów, które mogą być rozwiązane przez kilka prostych kroków.

-   **Przycisk aplety obciążenia jest widoczny.** Jeśli dodatek programu Excel ma **załadować apletów** przycisk po zalogowaniu, prawdopodobnie nie jesteś zalogowany jako poprawny użytkownik. Aby rozwiązać ten problem, sprawdź, czy poprawną nazwę użytkownika pojawia się w prawym górnym rogu dodatek programu Excel. Jeśli pojawi się niepoprawną nazwę użytkownika, kliknij go, wyloguj się, a następnie zaloguj się ponownie.
-   **Pojawi się komunikat "Dostęp zabroniony".** Jeśli zostanie wyświetlony komunikat "Dostęp zabroniony", podczas gdy dodatek programu Excel jest ładowanie metadanych, konto, na którym jest zalogowany do dodatek programu Excel nie ma uprawnień do używania usługi ukierunkowane, wystąpienie lub bazy danych. Aby rozwiązać ten problem, sprawdź, czy poprawną nazwę użytkownika pojawia się w prawym górnym rogu dodatek programu Excel. Jeśli pojawi się niepoprawną nazwę użytkownika, kliknij go, wyloguj się, a następnie zaloguj się ponownie.
-   **Pusta strona sieci Web jest wyświetlany w programie Excel.** Jeżeli pusta strona sieci Web otwiera się podczas procesu logowania, konto wymaga programu AD FS, ale używanej wersji programu Excel, który jest uruchomiony dodatek nie jest dokonana, aby załadować znak w oknie dialogowym. Aby rozwiązać ten problem, należy zaktualizować wersji programu Excel, którego używasz. Aby zaktualizować wersji programu Excel, gdy jesteś w przedsiębiorstwie na kanale odroczonego, użyj [narzędzia wdrażania pakietu Office](https://technet.microsoft.com/library/jj219422.aspx) do [przenieść z odroczonego kanału do bieżącego kanału](https://technet.microsoft.com/library/mt455210.aspx).



