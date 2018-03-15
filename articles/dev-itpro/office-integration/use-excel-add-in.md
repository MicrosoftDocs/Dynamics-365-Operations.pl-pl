---
title: "Używanie dodatku programu Excel"
description: "W tym temacie wyjaśniono, jak otwierać dane jednostek w programie Microsoft Excel, a następnie wyświetlać, aktualizować i edytować te dane przy użyciu dodatku pakietu Office dla usługi Microsoft Dynamics dla programu Excel."
author: ChrisGarty
manager: AnnBe
ms.date: 11/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 267914
ms.assetid: 4e6c7194-a059-4057-bd62-ec0c802c36fd
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 002c3bea2803fdf43b0c35620c8d46fc9400fafc
ms.openlocfilehash: 9db4f7ed9cba0d91a9a8507a33882a9114bdb1f5
ms.contentlocale: pl-pl
ms.lasthandoff: 01/04/2018

---

# <a name="use-the-excel-add-in"></a>Używanie dodatku programu Excel

[!include[banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak otwierać dane jednostek w programie Microsoft Excel, a następnie wyświetlać, aktualizować i edytować te dane przy użyciu dodatku pakietu Office dla usługi Microsoft Dynamics dla programu Excel. Aby otworzyć dane jednostki, można zacząć z poziomu programu Excel lub Microsoft Dynamics 365 for Finance and Operations Enterprise Edition.

Otwierając dane jednostek w programie Excel, można łatwo i szybko wyświetlić i edytować te dane przy użyciu dodatku dla programu Excel. Ten dodatek wymaga programu Microsoft Excel 2016.

> [!NOTE]
> Jeśli dzierżawa usługi Microsoft Azure Active Directory (Azure AD) jest skonfigurowana do używania usług federacyjnych w usłudze Active Directory (AD FS), należy się upewnić, że zastosowano aktualizację z maja 2016 r. dla pakietu Office, ponieważ tylko wtedy dodatek programu Excel będzie poprawnie logował użytkowników.

## <a name="open-entity-data-in-excel-when-you-start-from-finance-and-operations"></a>Otwieranie danych jednostki w programie Excel przy rozpoczynaniu z rozwiązania Finance and Operations
1. Na stronie w rozwiązaniu Finance and Operations wybierz opcję **Otwórz w pakiecie Microsoft Office**.

    Jeśli główne źródło danych (tabela) na stronie jest takie same, jak główne źródło danych którychkolwiek jednostek, dla strony zostaną wygenerowane domyślnie opcje **Otwórz w programie Excel**. Opcje **Otwórz w programie Excel** można znaleźć na często używanych stronach, takich jak **Wszyscy dostawcy** i **Wszyscy odbiorcy**.
 
2. Wybierz opcję **Otwórz w programie Excel**, a następnie otwórz wygenerowany skoroszyt. Ten skoroszyt zawiera informacje o powiązaniu jednostki, wskaźnik do środowiska oraz wskaźnik do dodatku programu Excel.
3. W programie Excel wybierz opcję **Włącz edytowanie**, co umożliwi uruchamianie dodatku programu Excel. Dodatek programu Excel jest uruchamiany w okienku z prawej strony okna programu Excel.
4. Jeśli uruchamiasz dodatek programu Excel po raz pierwszy, wybierz opcję **Ufaj temu dodatkowi**.
5. Jeśli zostanie wyświetlony monit o zalogowanie, wybierz opcję **Zaloguj**, a następnie zaloguj się przy użyciu tych samych poświadczeń, jak używane do logowania w rozwiązaniu Finance and Operations. Jeżeli jest to możliwe, dodatek programu Excel użyje poprzedniego kontekstu logowania z programu Internet Explorer i automatycznie Cię zaloguje. W związku z tym sprawdź nazwę użytkownika w prawym górnym rogu dodatku programu Excel.

Dodatek programu Excel automatycznie odczytuje dane wybranej jednostki. Należy zauważyć, że nie będzie żadnych danych w skoroszycie, dopóki dodatek programu Excel ich nie wczyta.

## <a name="open-entity-data-in-excel-when-you-start-from-excel"></a>Otwieranie danych jednostki w programie Excel przy rozpoczynaniu z programu Excel
1. W programie Excel na karcie **Wstaw** w grupie **Dodatki** wybierz opcję **Sklep**, co spowoduje otwarcie Sklepu Office.
2. W Sklepie Office wyszukaj według słowa kluczowego **Dynamics**, a następnie wybierz opcję **Dodaj** obok pozycji **Dodatek pakietu Office dla usługi Microsoft Dynamics** (dodatek programu Excel).
3. Jeśli uruchamiasz dodatek programu Excel po raz pierwszy, wybierz opcję **Ufaj temu dodatkowi**, co umożliwi uruchamianie dodatku. Dodatek programu Excel jest uruchamiany w okienku z prawej strony okna programu Excel.
4. Wybierz opcję **Dodaj informacje dotyczące serwera**, co spowoduje otwarcie okienka **Opcje**.
5. W przeglądarce skopiuj adres URL docelowego wystąpienia rozwiązania Finance and Operations, wklej go w polu **Adres URL serwera**, a następnie usuń wszystko po nazwie hosta. Powstały adres URL powinien zawierać tylko nazwę hosta.

    Jeżeli na przykład adres URL to `https://xxx.dynamics.com/?cmp=usmf&amp;mi=CustTableListPage`, usuń wszystko oprócz `https://xxx.dynamics.com`.

6. Wybierz przycisk **OK**, a następnie przycisk **Tak**, aby potwierdzić zmianę. Dodatek programu Excel zostanie ponownie uruchomiony i załaduje metadane.

    Będzie teraz dostępny przycisk **Projekt**. Jeśli dodatek programu Excel zawiera przycisk **Ładuj aplety**, prawdopodobnie nie jesteś zalogowany jako poprawny użytkownik. Aby uzyskać więcej informacji, zobacz „Jest wyświetlany przycisk Ładuj aplety” w sekcji [Rozwiązywanie problemów](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/office-integration/use-excel-add-in#troubleshooting) w tym temacie.

7. Wybierz opcję **Projekt** Dodatek programu Excel pobierze metadane jednostki.
8. Wybierz opcję **Dodaj tabelę**. Zostanie wyświetlona lista jednostek. Jednostki są wyświetlane w formacie „Nazwa — Etykieta”.
9. Na liście zaznacz jednostkę, taką jak **Odbiorca — Odbiorcy**, a następnie wybierz przycisk **Dalej**.
10. Aby dodać pole z listy **Dostępne pola** do listy **Wybrane pola**, wybierz pole, a następnie wybierz przycisk **Dodaj**. Można też kliknąć dwukrotnie pole na liście **Dostępne pola**.
11. Po zakończeniu dodawania pól do listy **Wybrane pola** upewnij się, że kursor znajduje się w odpowiednim miejscu w arkuszu (na przykład w komórce A1), a następnie wybierz opcję **Gotowe**. Następnie wybierz opcję **Gotowe**, aby zamknąć projektanta.
12. Wybierz opcję **Odśwież**, aby pobrać zestaw danych.

## <a name="view-and-update-entity-data-in-excel"></a>Wyświetlanie i aktualizowanie danych jednostki w programie Excel
Gdy dodatek programu Excel wczyta dane jednostki do skoroszytu, można w dowolnym momencie aktualizować te dane, wybierając opcję **Odśwież** w dodatku programu Excel.

## <a name="edit-entity-data-in-excel"></a>Edytowanie danych jednostki w programie Excel
Można zmienić dane jednostki w żądany sposób, a następnie opublikować je ponownie, wybierając opcję **Opublikuj** w dodatku programu Excel. Aby zmodyfikować rekord, zaznacz komórkę w arkuszu, a następnie zmień wartość komórki. Aby dodać nowy rekord, wykonaj jedną z następujących czynności:

- Kliknij w dowolnym miejscu tabeli źródeł danych, a następnie wybierz opcję **Nowy** w dodatku programu Excel.
- Kliknij gdziekolwiek w ostatnim wierszu tabeli źródeł danych, a następnie naciskaj klawisz Tab, aż kursor znajdzie się poza ostatnią kolumną tego wiersza i zostanie utworzony nowy wiersz.
- Kliknij gdziekolwiek w wierszu bezpośrednio poniżej tabelą źródeł danych i zacznij wprowadzać dane w komórce. Po przeniesieniu fokusu poza tę komórkę tabela powiększy się o nowy wiersz.
- W celu powiązania pól rekordów nagłówka wybierz jedno z pól, a następnie wybierz opcję **Nowy** w dodatku programu Excel.

Należy zauważyć, że nowy rekord można utworzyć tylko wtedy, gdy wszystkie pola wymagane są powiązane w arkuszu lub gdy wartości domyślne zostały wprowadzone przy użyciu warunku filtra.

Aby usunąć rekord, wykonaj jedną z następujących czynności:

- Kliknij prawym przyciskiem myszy numer wiersza obok wiersza arkusza, który chcesz usunąć, i wybierz opcję **Usuń**.
- Kliknij prawym przyciskiem myszy gdziekolwiek w wierszu arkusza, który chcesz usunąć, i wybierz opcję **Usuń** &gt; **Wiersze tabeli**.

Jeśli źródła danych zostały dodane jako pokrewne źródła danych, nagłówek jest publikowany przed wierszami. Jeśli istnieją zależności między innymi źródłami danych, może być konieczna zmiana domyślnej kolejności publikowania. Aby zmienić kolejność publikowania, w dodatku programu Excel wybierz przycisk **Opcje** (symbol koła zębatego), a następnie na skróconej karcie **Łącznik danych** wybierz opcję **Konfiguruj kolejność publikowania**.

## <a name="add-or-remove-columns"></a>Dodaj lub usuń kolumny
Można użyć projektanta, aby dostosować kolumny dodawane automatycznie do arkusza.

> [!NOTE]
> Jeżeli przycisk **Projekt** nie jest wyświetlany pod przyciskiem **Filtr** w dodatku programu Excel, należy włączyć projektanta danych źródłowych. Wybierz przycisk **Opcje** (symbol koła zębatego), a następnie zaznacz pole wyboru **Włącz projekt**.

1. W dodatku programu Excel wybierz opcję **Projekt**. Zostaną wyświetlone wszystkie źródła danych.
2. Obok źródła danych wybierz przycisk **Edytuj** (symbol ołówka).
3. Na liście **Wybrane pola** dostosuj listę pól według potrzeb:

    - Aby dodać pole z listy **Dostępne pola** do listy **Wybrane pola**, wybierz pole, a następnie wybierz przycisk **Dodaj**. Można też kliknąć dwukrotnie pole na liście **Dostępne pola**.
    - Aby usunąć pole z listy **Wybrane pola**, zaznacz pole i wybierz opcję **Usuń**. Alternatywnie kliknij dwukrotnie pole.
    - Aby zmienić kolejność pól na liście **Wybrane pola**, wybierz pole a następnie wybierz opcję **W górę** lub **W dół**.

4. Aby zastosować zmiany do źródła danych, wybierz opcję **Aktualizuj**. Następnie wybierz opcję **Gotowe**, aby zamknąć projektanta.
5. Jeśli dodano pole (kolumnę), wybierz opcję **Odśwież**, aby pobrać zaktualizowany zbiór danych.

## <a name="copy-environment-data"></a>Kopiuj dane środowiska

Dane wczytane do arkusza z jednego środowiska można skopiować do innego środowiska. Nie wystarczy jedna zmienić adresu URL połączenia, ponieważ pamięć podręczna danych w skoroszycie będzie nadal traktować dane jako istniejące. Zamiast tego należy użyć funkcji Kopiuj dane środowiska, aby opublikować dane w nowych środowisku jako nowe dane.

1. Wybierz przycisk **Opcje** (symbol koła zębatego), a następnie na skróconej karcie **Łącznik danych** wybierz opcję **Kopiuj dane środowiska**. 
2. Wprowadź adres URL serwera dla nowego środowiska. 
3. Wybierz przycisk **OK**, a następnie przycisk **Tak**, aby potwierdzić akcję. Dodatek programu Excel zostanie uruchomiony ponownie i połączy się z nowym środowiskiem. Wszystkie dane istniejące w skoroszycie są traktowane jak nowe dane.

    Po ponownym uruchomieniu dodatku programu Excel zostanie wyświetlony komunikat z informacją, że skoroszyt działa w trybie kopiowania środowiska.

4. Aby skopiować dane do nowego środowiska jako nowe dane, wybierz opcję **Opublikuj**. Aby anulować operację kopiowania środowiska i przejrzeć istniejące dane w nowym środowisku, wybierz opcję **Odśwież**.

## <a name="troubleshooting"></a>Rozwiązywanie problemów
Istnieje kilka problemów, które można rozwiązać poprzez wykonanie kilku prostych kroków.

- **Przycisk Ładuj aplety jest widoczny** — jeśli po zalogowaniu dodatek programu Excel zawiera przycisk **Ładuj aplety**, prawdopodobnie nie jesteś zalogowany jako poprawny użytkownik. Aby rozwiązać ten problem, sprawdź, czy w prawym górnym rogu dodatku programu Excel jest wyświetlana poprawna nazwa użytkownika. Jeśli widać niepoprawną nazwę użytkownika, wybierz ją, wyloguj się, a następnie zaloguj ponownie.
- **Wyświetlany jest komunikat „Zabronione”** — jeśli podczas ładowania metadanych przez dodatek programu Excel zostanie wyświetlony komunikat „Zabronione”, oznacza to, że konto zalogowane do dodatku programu Excel nie ma uprawnień do używania docelowej usługi, wystąpienia lub bazy danych. Aby rozwiązać ten problem, sprawdź, czy w prawym górnym rogu dodatku programu Excel jest wyświetlana poprawna nazwa użytkownika. Jeśli widać niepoprawną nazwę użytkownika, wybierz ją, wyloguj się, a następnie zaloguj ponownie.
- **W programie Excel jest wyświetlana pusta strona internetowa** — jeśli w trakcie procesu logowania otwiera się pusta strona sieci Web, konto wymaga usług AD FS, ale wersja programu Excel, w której jest uruchomiony dodatek programu Excel, jest zbyt stara, aby załadować okno dialogowe logowania. Aby rozwiązać ten problem, należy zaktualizować używaną wersję programu Excel. W celu zaktualizowania wersji programu Excel, gdy jesteś w przedsiębiorstwie znajdującym się w odroczonym kanale, użyj [narzędzia wdrażania pakietu Office](https://technet.microsoft.com/library/jj219422.aspx), aby [przełączyć z kanału odroczonego do bieżącego](https://technet.microsoft.com/library/mt455210.aspx).

