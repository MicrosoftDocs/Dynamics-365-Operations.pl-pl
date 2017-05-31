---
title: "Używanie dodatku programu Excel"
description: "W tym temacie wyjaśniono, jak otwierać dane jednostek w programie Microsoft Excel, a następnie wyświetlać, aktualizować i edytować te dane przy użyciu dodatku pakietu Office dla usługi Microsoft Dynamics dla programu Excel. Aby otworzyć dane jednostki, można zacząć z poziomu programu Excel lub Microsoft Dynamics 365 for Operations."
author: ChrisGarty
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 267914
ms.assetid: 4e6c7194-a059-4057-bd62-ec0c802c36fd
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: c391fb70d837db9c0f167b392291fc1c5cc2bb53
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="use-the-excel-add-in"></a>Używanie dodatku programu Excel

[!include[banner](../includes/banner.md)]


W tym temacie wyjaśniono, jak otwierać dane jednostek w programie Microsoft Excel, a następnie wyświetlać, aktualizować i edytować te dane przy użyciu dodatku pakietu Office dla usługi Microsoft Dynamics dla programu Excel. Aby otworzyć dane jednostki, można zacząć z poziomu programu Excel lub Microsoft Dynamics 365 for Operations.

Otwierając dane jednostek w programie Microsoft Excel, można łatwo i szybko wyświetlić i edytować te dane przy użyciu dodatku pakietu Office dla usługi Microsoft Dynamics dla programu Excel. Ten dodatek wymaga programu Microsoft Excel 2016. **Uwaga:** Jeśli dzierżawa usługi Microsoft Azure Active Directory (Azure AD) jest skonfigurowana do używania usług federacyjnych w usłudze Active Directory (AD FS), należy się upewnić, że zastosowano aktualizację z maja 2016 r., ponieważ tylko wtedy dodatek programu Excel będzie poprawnie logował użytkowników.

## <a name="open-entity-data-in-excel-when-you-start-from-dynamics-365-for-operations"></a>Otwieranie danych jednostki w programie Excel przy rozpoczynaniu z programu Dynamics 365 for Operations
1.  Na stronie w usłudze Microsoft Dynamics 365 for Operations kliknij przycisk **Otwórz w pakiecie Microsoft Office**. Jeśli główne źródło danych (tabela) na stronie jest takie same, jak główne źródło danych którychkolwiek jednostek, dla strony zostaną wygenerowane domyślnie opcje **Otwórz w programie Excel**. Opcje **Otwórz w programie Excel** można znaleźć na często używanych stronach, takich jak **Wszyscy dostawcy** i **Wszyscy odbiorcy**.
2.  Kliknij opcję **Otwórz w programie Excel**, a następnie otwórz wygenerowany skoroszyt. Ten skoroszyt zawiera informacje o powiązaniu jednostki, wskaźnik do środowiska oraz wskaźnik do dodatku programu Excel.
3.  W programie Excel kliknij przycisk **Włącz edytowanie**, co umożliwi uruchamianie dodatku programu Excel. Dodatek programu Excel jest uruchamiany w okienku z prawej strony okna programu Excel.
4.  Jeśli uruchamiasz dodatek programu Excel po raz pierwszy, kliknij opcję **Ufaj temu dodatkowi**.
5.  Jeśli zostanie wyświetlony monit o zalogowanie, kliknij przycisk **Zaloguj**, a następnie zaloguj się przy użyciu tych samych poświadczeń, jak używane do logowania w programie Dynamics 365 for Operations. Jeżeli jest to możliwe, dodatek programu Excel użyje poprzedniego kontekstu logowania z programu Internet Explorer i automatycznie Cię zaloguje. W związku z tym sprawdź nazwę użytkownika w prawym górnym rogu dodatku programu Excel.

Dodatek programu Excel automatycznie odczytuje dane wybranej jednostki. Należy zauważyć, że nie będzie żadnych danych w skoroszycie, dopóki dodatek programu Excel ich nie wczyta.

## <a name="open-entity-data-in-excel-when-you-start-from-excel"></a>Otwieranie danych jednostki w programie Excel przy rozpoczynaniu z programu Excel
1.  W programie Excel na karcie **Wstaw** w grupie **Dodatki** kliknij opcję **Sklep**, co spowoduje otwarcie Sklepu Office.
2.  W Sklepie Office wyszukaj według słowa kluczowego „Dynamics”, a następnie kliknij przycisk **Dodaj** obok pozycji **Dodatek pakietu Office dla usługi Microsoft Dynamics** (lub Microsoft Dynamics Office Add-in). Jest to żądany dodatek programu Excel.
3.  Jeśli uruchamiasz dodatek programu Excel po raz pierwszy, kliknij opcję **Ufaj temu dodatkowi**, co umożliwi uruchamianie dodatku. Dodatek programu Excel jest uruchamiany w okienku z prawej strony okna programu Excel.
4.  Kliknij opcję **Dodaj informacje dotyczące serwera**, co spowoduje otwarcie okienka **Opcje**.
5.  W przeglądarce skopiuj adres URL docelowego wystąpienia programu Dynamics 365 for Operations, wklej go w polu **Adres URL serwera**, a następnie usuń wszystko po nazwie hosta. Powstały adres URL powinien zawierać tylko nazwę hosta.
Na przykład jeśli adres URL to https://xxx.dynamics.com/?cmp=usmf&amp;mi=CustTableListPage, usuń wszystko poza fragmentem **https://xxx.dynamics.com**.
6.  Kliknij przycisk **OK**, a następnie przycisk **Tak**, aby potwierdzić zmianę. Dodatek programu Excel zostanie ponownie uruchomiony i załaduje metadane. Będzie teraz dostępny przycisk **Projekt**. Jeśli dodatek programu Excel zawiera przycisk **Ładuj aplety**, prawdopodobnie nie jesteś zalogowany jako poprawny użytkownik. Aby uzyskać więcej informacji, zobacz „Jest wyświetlany przycisk Ładuj aplety” w sekcji „Rozwiązywanie problemów” w tym temacie.
7.  Kliknij przycisk **Projekt**. Dodatek programu Excel pobierze metadane jednostki.
8.  Kliknij opcję **Dodaj tabelę**. Zostanie wyświetlona lista jednostek. Jednostki są wyświetlane w formacie „Nazwa — Etykieta”.
9.  Na liście zaznacz jednostkę, taką jak **Odbiorca — Odbiorcy**, a następnie kliknij przycisk **Dalej**.
10. Aby dodać pole z listy **Dostępne pola** do listy **Wybrane pola**, kliknij pole, a następnie kliknij przycisk **Dodaj**. Alternatywnie kliknij dwukrotnie pole.
11. Po zakończeniu dodawania pól do listy **Wybrane pola** upewnij się, że kursor znajduje się w odpowiednim miejscu w arkuszu (na przykład w komórce A1), a następnie kliknij przycisk **Gotowe**. Następnie kliknij przycisk **Gotowe**, aby zamknąć projektanta.
12. Kliknij przycisk **Odśwież**, aby pobrać zestaw danych.

## <a name="view-and-update-entity-data-in-excel"></a>Wyświetlanie i aktualizowanie danych jednostki w programie Excel
Gdy dodatek programu Excel wczyta dane jednostki do skoroszytu, można w dowolnym momencie aktualizować te dane, klikając przycisk **Odśwież** w dodatku programu Excel.

## <a name="edit-entity-data-in-excel"></a>Edytowanie danych jednostki w programie Excel
Można zmienić dane jednostki w żądany sposób, a następnie opublikować je ponownie, klikając przycisk **Opublikuj** w dodatku programu Excel. Aby zmodyfikować rekord, zaznacz komórkę w arkuszu, a następnie zmień wartość komórki. Aby dodać nowy rekord, wykonaj jedną z następujących czynności:

-   Kliknij w dowolnym miejscu tabeli źródeł danych, a następnie kliknij przycisk **Nowy** w dodatku programu Excel.
-   Kliknij w ostatnim wierszu tabeli źródeł danych, a następnie naciskaj klawisz Tab, aż kursor znajdzie się poza ostatnią kolumną tego wiersza i zostanie utworzony nowy wiersz.
-   Kliknij w wierszu bezpośrednio poniżej tabelą źródeł danych i zacznij wprowadzać dane w komórce. Po przeniesieniu fokusu poza tę komórkę tabela powiększy się o nowy wiersz.
-   W celu powiązania pól rekordów nagłówka kliknij jedno z pól, a następnie kliknij przycisk **Nowy** w dodatku programu Excel.

Należy zauważyć, że nowy rekord można utworzyć tylko wtedy, gdy wszystkie pola wymagane są powiązane w arkuszu lub gdy wartości domyślne zostały wprowadzone przy użyciu warunku filtra.
Aby usunąć rekord, wykonaj jedną z następujących czynności:

-   Kliknij prawym przyciskiem myszy numer wiersza obok wiersza arkusza, który chcesz usunąć, i kliknij przycisk **Usuń**.
-   Kliknij prawym przyciskiem myszy wiersz arkusza, który chcesz usunąć, i kliknij kolejno opcje **Usuń** &gt; **Wiersze tabeli**.
Jeśli źródła danych zostały dodane jako pokrewne, nagłówek jest publikowany przed wierszami. Jeśli istnieją zależności między innymi źródłami danych, może być konieczna zmiana domyślnej kolejności publikowania. Aby zmienić kolejność publikowania, w dodatku programu Excel kliknij przycisk **Opcje** (symbol koła zębatego). Następnie na skróconej karcie **Łącznik danych** kliknij opcję **Konfiguruj publikowanie zamówienia**.

## <a name="add-or-remove-columns"></a>Dodaj lub usuń kolumny
Można użyć projektanta, aby dostosować kolumny dodawane automatycznie do arkusza.

1.  Uruchom projektanta danych źródłowych dodatku programu Excel, klikając przycisk **Opcje** (symbol koła zębatego), a następnie zaznaczając pole wyboru **Włącz projekt**.
2.  W dodatku programu Excel kliknij opcję **Projekt**. Zostaną wyświetlone wszystkie źródła danych.
3.  Obok źródła danych kliknij przycisk **Edytuj** (symbol ołówka).
4.  Dostosuj pola na liście **Wybrane pola** w żądany sposób:
    -   Aby dodać pole z listy **Dostępne pola** do listy **Wybrane pola**, kliknij pole, a następnie kliknij przycisk **Dodaj**. Alternatywnie kliknij dwukrotnie pole.
    -   Aby usunąć pole z listy **Wybrane pola**, zaznacz pole i kliknij przycisk **Usuń**. Alternatywnie kliknij dwukrotnie pole.
    -   Aby zmienić kolejność pól, kliknij pole na liście **Wybrane pola**, a następnie kliknij przycisk **W górę** lub **W dół**.

5. Aby zastosować zmiany do źródła danych, kliknij przycisk **Aktualizuj**. Następnie kliknij przycisk **Gotowe**, aby zamknąć projektanta. 
6. Jeśli dodano pole (kolumnę), kliknij przycisk **Odśwież**, aby pobrać zaktualizowany zbiór danych.

## <a name="httpspowerappsmicrosoftcomenustutorialsdataplatforminteractiveexceltroubleshootingtroubleshooting"></a>[](https://powerapps.microsoft.com/enus/tutorials/dataplatforminteractiveexcel/#troubleshooting)Rozwiązywanie problemów
Istnieje kilka problemów, które można rozwiązać poprzez wykonanie kilku prostych kroków.

-   **Jest wyświetlany przycisk Ładuj aplety.** Jeśli po zalogowaniu dodatek programu Excel zawiera przycisk **Ładuj aplety**, prawdopodobnie nie jesteś zalogowany jako poprawny użytkownik. Aby rozwiązać ten problem, sprawdź, czy w prawym górnym rogu dodatku programu Excel jest wyświetlana poprawna nazwa użytkownika. Jeśli widać niepoprawną nazwę użytkownika, kliknij ją, wyloguj się, a następnie zaloguj ponownie.
-   **Pojawia się komunikat „Zabronione”.** Jeśli podczas ładowania metadanych przez dodatek programu Excel zostanie wyświetlony komunikat „Zabronione”, oznacza to, że konto zalogowane do dodatku programu Excel nie ma uprawnień do używania docelowej usługi, wystąpienia lub bazy danych. Aby rozwiązać ten problem, sprawdź, czy w prawym górnym rogu dodatku programu Excel jest wyświetlana poprawna nazwa użytkownika. Jeśli widać niepoprawną nazwę użytkownika, kliknij ją, wyloguj się, a następnie zaloguj ponownie.
-   **W programie Excel jest wyświetlana pusta strona internetowa.** Jeśli w trakcie procesu logowania otwiera się pusta strona sieci Web, konto wymaga usług AD FS, ale wersja programu Excel, w której jest uruchomiony dodatek, jest zbyt stara, aby załadować okno dialogowe logowania. Aby rozwiązać ten problem, należy zaktualizować używaną wersję programu Excel. W celu zaktualizowania wersji programu Excel, gdy jesteś w przedsiębiorstwie znajdującym się w odroczonym kanale, użyj [narzędzia wdrażania pakietu Office](https://technet.microsoft.com/library/jj219422.aspx), aby [przełączyć z kanału odroczonego do bieżącego](https://technet.microsoft.com/library/mt455210.aspx).





