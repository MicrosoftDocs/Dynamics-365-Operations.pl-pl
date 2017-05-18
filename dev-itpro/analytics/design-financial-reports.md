---
title: "Wyświetlanie i projektowanie raportów finansowych"
description: "Ten artykuł zawiera ćwiczenia, które prowadzą przez całą procedurę wyświetlania i tworzenia raportów finansowych w programie Microsoft Dynamics 365 for Operations."
author: jcart1106
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 10814
ms.assetid: cd5f6483-c09b-4c2d-9336-d22eb6ab6e4f
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6f785ac8b9a8be503bf9122f21716f745b17115b
ms.openlocfilehash: 635e9e90c63330b3d8b0cc46f16a36fa44ef915d
ms.contentlocale: pl-pl
ms.lasthandoff: 04/27/2017


---

# <a name="view-and-design-financial-reports"></a>Wyświetlanie i projektowanie raportów finansowych

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera ćwiczenia, które prowadzą przez całą procedurę wyświetlania i tworzenia raportów finansowych w programie Microsoft Dynamics 365 for Operations. Funkcjonalność sprawozdawczości finansowej składa się z funkcji wyświetlania w programie Dynamics 365 for Operations oraz aplikacji ClickOnce projektanta raportów, który umożliwia tworzenie i edytowanie raportów finansowych.  

<a name="exercise-1-generate-and-explore-a-default-financial-report"></a>Ćwiczenie 1: Generowanie i przeglądanie domyślnego raportu finansowego
-----------------------------------------------------------

W tym ćwiczeniu wygenerujemy i przejrzymy istniejący raport domyślny. Ten raport zawiera wszystkie konta i zawiera także właściwości (atrybuty) dla kont. Można będzie wyświetlić szczegóły, stosować filtry wymiarów, zmieniać walutę w raporcie. Najpierw zaktualizujemy kolejność wyświetlania wymiarów dla raportowania finansowego. Umożliwia to wybranie sposobu wyświetlania wymiarów nie tylko podczas projektowania i wyświetlania raportów finansowych.

1.  Przejdź do opcji **Konfiguracja wymiaru finansowego dla aplikacji integrujących** w sekcji **Wymiary planu kont** w księdze głównej.
2.  Ustaw wymiary w następującej kolejności:
    1.  Konto główne
    2.  Jednostka biznesowa
    3.  Centrum kosztu
    4.  Dział

    Uwaga: inne wymiary mogą pozostać w niezmienionej kolejności.
3.  Zapisz konfigurację wymiarów. Następnie wygenerujemy raport i przejrzymy dane w raporcie.
4.  Przejdź do opcji **Raporty finansowe** w sekcji **Zapytania i raporty** w księdze głównej.
5.  Wybierz wiersz dla raportu o nazwie **Szczegóły KG — domyślne.**
6.  Wybierz opcję **Edycja.** Uwaga: Pojawi się monit o pobranie i kliknięcie projektanta raportów w celu zalogowania się. Zaloguj się za pomocą swoich poświadczeń.
7.  Zmień rok bazowy 2012 i wybierz **Generuj**. Wygenerowany raport otworzy się w nowej karcie przeglądarki. Raport można przeglądać w nowej karcie przeglądarki, albo przejść do wyjściowej karty przeglądarki i otworzyć go tam, wybierając z listy **Raporty finansowe**.
8.  W otwartym raporcie wybierz jedną z kwot, aby wyświetlić szczegóły konta dla raportu.
9.  Po wyświetleniu szczegółów konta wybierz konto z danymi i **przejdź niżej do poziomu transakcji raportu**. Na poziomie transakcji raportu widać właściwości (atrybuty), które zostały dołączone do projektu tego raportu. W zależności od transakcji i konta mogą być wyświetlane niektóre lub wszystkie atrybuty.
10. Zamknij poziom transakcji raportu.
11. Wybierz to samo lub inne konto i **otwórz transakcje załącznika.** Transakcje załącznika są filtrowane według okresu, roku oraz kombinacji konta i wymiaru dla wybranego konta. Z poziomu transakcji załącznika możesz przeglądać inne informacje o transakcji.
12. Zamknij transakcje załącznika. W raporcie finansowym można wyświetlać dane dla innego okresu i roku lub po zastosowaniu różnych atrybutów i wymiarów. Służą do tego **Opcje raportowania**.
13. Wybierz **Opcje raportowania**.
14. Wybierz **Dodaj filtr wymiaru** i wybierz polecenie **Jednostka biznesowa**.
15. Typ 001 w polu i wybierz **OK**. Teraz w raporcie widać tylko dane dla jednostki biznesowej 001. To jest spersonalizowany widok raportu, który jest niedostępny dla innych użytkowników.
16. Zamknij filtrowany raport. Raporty finansowe mogą być wyświetlane w dowolnej walucie, która została dodana do programu Dynamics 365 for Operations.
17. Wybierz opcję **Waluta**, a następnie wybierz **EUR.** Teraz raport jest wyświetlany w euro. Wszelkie kody i symbole waluty uwzględnione w projekcie raportu są teraz wyświetlane w zastosowanej walucie. Jeśli dla waluty nie zdefiniowano symbolu, symbol waluty nie jest wyświetlany.
18. Zamknij raport **Szczegóły KG**.
19. Zamknij **Projektanta raportów**.

## <a name="exercise-2-add-additional-account-properties-to-a-report-design"></a>Ćwiczenie 2: Dodawanie dodatkowych właściwości konta do projektu raportu
W tym ćwiczeniu zmodyfikujemy istniejący raport domyślny. Zaktualizujesz zarówno definicję wiersza, tak aby zawierała wszystkie konta, jak i definicję kolumny, tak aby zawierała atrybuty konta. Po zakończeniu aktualizacji wygenerujesz nowo utworzony raport i przejrzysz jego treść. Zaczniemy od listy Raporty finansowe.

1.  Przejdź do opcji **Raporty finansowe** w sekcji Zapytania i raporty w księdze głównej.
2.  Wybierz wiersz dla raportu o nazwie **Sumaryczny bilans próbny — domyślny**
3.  Wybierz opcję **Edycja**. **Sumaryczny bilans próbny — domyślny** zostanie otwarty w Projektancie raportów.
4.  Wybierz **Plik**, a następnie **Zapisz jako** i nazwij raport „Szczegółowy bilans próbny z atrybutami”. Uwaga: Za każdym razem, gdy tworzony jest nowy raport w projektancie raportów, lista raportów finansowych w programie Dynamics 365 for Operations jest aktualizowana.
5.  Z poziomu definicji raportu wybierz ikonę definicji wiersza, aby otworzyć **Bilans próbny — domyślna definicja wiersza**.
6.  Zapisz definicję wiersza jako **Szczegółowy bilans próbny z atrybutami**
7.  Umieść kursor w wierszu 50, zaznacz opcję **Edycja**, a następnie **Wstaw wiersze z wymiarów**. Polecenie „Wstaw wiersze z wymiarów” pozwala wybrać wymiary dostępne w definicji wiersza. W tym ćwiczeniu zbudujemy definicję wiersza za pomocą Konta głównego.
8.  Upewnij się, że **Konto główne** zawiera wszystkie znaki „&”, a następnie wybierz **OK**. Teraz definicja wiersza zawiera wszystkie konta główne dla firmy USMF.
9.  Przewiń w dół do wiersza 11110 i usuń wiersz 11110.
10. W wierszu 11080 zaznacza **--- (podkreśl kwoty)**.
11. W wierszu 11140 wpisz **Suma wszystkich kont** w kolumnie B.
12. W kolumnie C wybierz **TOT** z listy rozwijanej.
13. Typ **50:11080** w kolumnie D.
14. **Zapisz** definicję wiersza. Teraz definicja wiersza zawiera wszystkie konta oraz wiersz sumy, aby dodać wszystkie konta ze sobą. Następnie zaktualizujemy definicję kolumny, aby zawierała dodatkowe atrybuty konta.
15. Z poziomu definicji raportu **Szczegółowy bilans próbny z atrybutami** wybierz ikonę definicji kolumny i otwórz definicję kolumny **Sumaryczny bilans próbny — domyślny**.
16. Zapisz definicję kolumny jako **Szczegółowy bilans próbny z atrybutami**. Definicja kolumny zawiera kolumny danych finansowych, kolumnę opisu oraz kolumny obliczeń. Dodamy kolumny atrybutu do definicji kolumny, aby udostępnić dodatkowe szczegóły dotyczące kont.
17. Następujące atrybuty zostaną dodane do definicji kolumny:
    -   Numer arkusza
    -   Opis arkusza
    -   Data transakcji
    -   Utworzone przez
    -   Autor ostatniej modyfikacji

18. W kolumnie I wybierz **ATTR** jako typ kolumny. Następnie wybierz **Numer arkusza** jako kategorię atrybutu.
19. Kontynuuj dodawanie kolumn dla pozostałych atrybutów.
20. W wierszu **Nagłówek 2** dodaj opisy dla każdej nowej kolumny, która została dodana.
21. Zapisz definicję kolumny. Teraz, gdy definicje wiersza i kolumny zostały zaktualizowane, będziemy musieli dodać je do definicji raportu.
22. Z poziomu definicji raportu **Szczegółowy bilans próbny z atrybutami** wybierz Szczegółowy bilans próbny z atrybutami zarówno dla definicji wiersza, jak i dla definicji kolumny.
23. Zmień rok podstawowy na **2012.**
24. **Zapisz** definicję raportu i **wygeneruj** raport. Po wygenerowaniu i otwarciu raportu możesz przejrzeć jego zawartość tak samo, jak w pierwszym ćwiczeniu. Przejdź do szczegółów różnych kont, aby zobaczyć sposób wyświetlania dodatkowych atrybutów.
25. Zamknij raport **Szczegółowy bilans próbny z atrybutami**.
26. Zamknij **Projektanta raportów**.

## <a name="exercise-3-create-a-multidimensional-report-using-a-reporting-tree"></a>Ćwiczenie 3: Tworzenie wielowymiarowego raportu za pomocą drzewa raportowania
W tym ćwiczeniu zmodyfikujemy istniejący raport domyślny. Będziemy tworzyli drzewo raportowania i dodawali do definicji raportu, aby wygenerować Rachunek wyników dla centrum kosztu/wymiaru. Po wprowadzeniu zmian wygenerujemy Rachunek wyników dla centrum kosztu/wymiaru i zapoznamy się z jego zawartością za pomocą drzewa raportowania. Zaczniemy od listy Raporty finansowe.

1.  Przejdź do opcji **Raporty finansowe** w sekcji Zapytania i raporty w księdze głównej.
2.  Wybierz wiersz dla raportu o nazwie **Rachunek wyników — domyślny**
3.  Wybierz opcję **Edycja**. **Rachunek wyników — domyślny** otworzy się w projektancie raportów.
4.  W menu **Plik** wybierz **Nowy**, a następnie kliknij polecenie **Definicja drzewa raportowania**.
5.  W menu **Edycja** kliknij **Wstaw jednostki raportowania z wymiarów**...
6.  Wyczyść pola wyboru dla wszystkich wymiarów z wyjątkiem **Centrum kosztu**.
7.  Kliknij pole **Z wymiaru** dla wymiaru Centrum kosztu, wpisz **007**, a następnie naciśnij klawisz Tab. W polu **Do wymiaru** wpisz **018**.
8.  **Zapisz** otrzymane drzewo pod nazwą **Centra kosztu wg działu**. Teraz, gdy drzewo raportowania jest już utworzone, trzeba je zmodyfikować, by zawierało trzy jednostki akumulacji; Marketing, Operacje i Sieć sprzedaży.
9.  W menu **Okno** kliknij **Centra kosztu wg działu**. (Jeśli drzewo raportowania zostało zamknięte, wybierz je z Definicji drzew raportowania w okienku nawigacji).
10. Kliknij numer jednostki, **Targi** i kliknij ikonę **Wstaw jednostkę raportowania**.
11. Kliknij dwukrotnie kolumnę jednostki w pustym wierszu i wybierz **USMF**.
12. W kolumnach B i C wpisz **Marketing**.
13. Kliknij numer jednostki 5 **Operacje usług** i kliknij prawym przyciskiem myszy. Wybierz **Wstaw jednostkę raportowania**.
14. Powtórz krok 11.
15. W kolumnach B i C wpisz **Operacje**.
16. Kliknij numer jednostki 12, **Outlet** i kliknij prawym przyciskiem myszy. Wybierz **Wstaw jednostkę raportowania**.
17. Powtórz krok 11.
18. Wpisz **Sieć sprzedaży** w kolumnach B i C. Zwróć uwagę, że jednostki Marketing, Operacje i Sieć sprzedaży wyświetlają ten sam poziom co bieżące jednostki zestawienia. Dalej nowej jednostki są organizowane. Jednostki raportowania są organizowane za pomocą menu kontekstowego; ponoszenia lub obniżania poziomu lub przeciągania i upuszczania.
19. Sprawdź, czy jednostka 3, **Targi**, jeśli aktywna i kliknij prawym przyciskiem myszy.
20. Wybierz **Obliż poziom jednostkę raportowania**. Zwróć uwagę, że teraz jednostka wyświetla się jako podrzędna dla **Marketingu**.
21. Kliknij jednostkę 4, **Kampania** **marketingowa**, i kliknij prawym przyciskiem myszy.
22. Wybierz **Obliż poziom jednostkę raportowania**.
23. Kliknij **Operacje usług** w widoku graficznym. Naciśnij i przytrzymaj lewy przycisk myszy podczas przeciągania jednostki do **Operacji**. Zwolnij lewy przycisk myszy, aby umieścić jednostkę w zestawieniu Operacji. Powtórz dla **Produkcji, Kontroli jakości, Logistyki, Zaopatrzenia i Administracji**.
24. Ustaw **Outlet**, **Super**, **Centrum handlowe** i **Online** jako podrzędne dla **Sieci sprzedaży**, obniżając poziom lub przeciągając i upuszczając.
25. Zapisz otrzymaną nową organizację. Teraz, gdy mamy utworzone i zorganizowane drzewo raportowania, można je dodać do definicji raportu.
26. W menu **Okno** wybierz **Rachunek wyników — domyślny**, aby otworzyć definicję raportu.
27. Kliknij strzałkę rozwijaną **Typ drzewa** i wybierz **Drzewo raportowania**.
28. Kliknij strzałkę rozwijaną drzewa i wybierz **Centra kosztu wg działu**.
29. Zmienia rok podstawowy na **2012**, **zapisz** zmiany i **wygeneruj** raport. Po otarciu wygenerowanego raportu możesz sprawdzić jego zawartość.
30. Wybierz menu rozwijane **Drzewo raportowania**, aby wyświetlić jednostki raportowania. Możesz też wyświetlić szczegóły w wierszu raportu, aby zobaczyć wszystkie salda dla wszystkich jednostek drzewa raportowania.
31. Zamknij **Raport wyników — domyślny**.
32. Zamknij **Projektanta raportów**.

## <a name="exercise-4-create-a-consolidated-report-using-an-organization-hierarchy"></a>Ćwiczenie 4: Tworzenie skonsolidowanego raportu przy użyciu hierarchii organizacyjnej
W tym ćwiczeniu zmodyfikujemy istniejący raport domyślny. Dodasz hierarchię organizacyjną do definicji raportu, aby wygenerować raporty Skonsolidowany rachunek wyników i bilans Po wprowadzeniu zmian wygenerujesz skonsolidowany raport i zapoznasz się z jego zawartością za pomocą drzewa raportowania. Zaczniemy od listy Raporty finansowe.

1.  Przejdź do opcji **Raporty finansowe** w sekcji Zapytania i raporty w księdze głównej.
2.  Wybierz wiersz raportu o nazwie **Bilans i rachunek wyników obok siebie — domyślny**
3.  Wybierz opcję **Edycja**. Raport **Bilans i rachunek wyników obok siebie — domyślny** otworzy się w projektancie raportów.
4.  Wybierz kolejno opcje **Plik** &gt; **Zapisz jako** i nazwij raport **Skonsolidowany bilans i rachunek wyników obok siebie**.
5.  Zmień rok podstawowy na 2012.
6.  Kliknij strzałkę rozwijaną typu drzewa i wybierz **Hierarchie organizacyjne**.
7.  Kliknij strzałkę rozwijaną typu drzewa i wybierz **Holdingi Contoso**.
8.  Zapisz zmiany i wygeneruj raport. Po wyświetleniu monitu wybierz wszystkie jednostki raportowania. Po otarciu wygenerowanego raportu możesz sprawdzić jego zawartość.
9.  Wybierz **Opcje raportowania**.
10. Wybierz **Dodaj filtr wymiaru** i wybierz polecenie **Dział**.
11. Typ **022** w polu i wybierz **OK**.
12. Zamknij filtrowany raport.
13. Wybierz menu rozwijane **Drzewo raportowania**, aby wyświetlić jednostki raportowania. Możesz też wyświetlić szczegóły w wierszu raportu, aby zobaczyć wszystkie salda dla wszystkich jednostek drzewa raportowania.
14. Zamknij raport **Skonsolidowany bilans i rachunek wyników obok siebie**.
15. Zamknij **Projektanta raportów**.

## <a name="exercise-5-create-a-sidebyside-departmental-report"></a>Ćwiczenie 5: Tworzenie raportu wg działów obok siebie
W tym ćwiczeniu utworzymy nowy raport. Raport jest rachunkiem wyników działu wyświetlanym obok siebie. Użyjemy istniejącej definicji wiersza, ale utworzymy nową definicję raportu i nową definicję kolumny, które będą korzystały z filtrów wymiarów. Zaczniemy od listy Raporty finansowe.

1.  Przejdź do opcji **Raporty finansowe** w sekcji Zapytania i raporty w księdze głównej.
2.  Wybierz **Nowy**. Projektant raportów otworzy się z otwartą pustą definicją raportu. Najpierw utworzysz definicję kolumny.
3.  Utwórz nową definicję kolumny, klikając **Plik**, następnie **Nowy**, a następnie **Definicja kolumny**.
4.  W **Kolumnie A** wybierz **DESC** jako typ kolumny.
5.  W **Kolumnie B** wybierz **FD** jako typ kolumny.
6.  Kliknij dwukrotnie w polu **Filtr wymiaru**.
7.  W oknie **Wymiar** kliknij dwukrotnie kolumnę **Dział**.
8.  W sekcji Pojedynczy lub zakres okna dialogowego kliknij **wielokropek** dla pola **Z**, aby wyświetlić listę działów.
9.  Wybierz dział **022**, **Sprzedaż i marketing**, a następnie kliknij **OK**.
10. Powtórz kroki od 5 do 8 dla działów 23-25.
11. W wierszu **Nagłówek 2** dla każdej kolumny FD, wpisz następujące opisy działów:
    -   Kolumna B – Sprzedaż i marketing
    -   Kolumna C — Operacje
    -   Kolumna D – Finanse
    -   Kolumna E – IT

12. Zapisz definicję kolumny jako Działy obok siebie. Ponieważ używamy istniejącej definicji wiersza, możemy zmodyfikować definicję raportu, aby korzystać z nowo utworzonej definicji kolumny i istniejącej definicji wiersza.
13. W menu **Okno** wybierz **Nowa definicja raportu**, aby otworzyć definicję raportu.
14. Wybierz **Rachunek wyników — domyślny** jako definicję wiersza i **Działy obok siebie** jako definicję kolumny.
15. Zapisz definicję raportu jako **Rachunek wyników działu obok siebie**.
16. Zmień rok podstawowy na **2012**.
17. Zmień poziom szczegółów na **Finanse, konto i transakcja**.
18. **Zapisz** zmiany i **wygeneruj**. Po otarciu wygenerowanego raportu możesz sprawdzić jego zawartość.

## <a name="additional-resources"></a>Dodatkowe zasoby
[Raportowanie finansowe](/dynamics365/operations/financials/general-ledger/financial-reporting-getting-started) 
[Wyświetlanie raportów finansowych](/dynamics365/operations/financials/general-ledger/view-financial-reports) 
[Blog o sprawozdawczości finansowej w systemie Dynamics](http://blogs.msdn.com/b/dynamics_financial_reporting/)




