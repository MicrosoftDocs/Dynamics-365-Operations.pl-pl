---
title: Przeglądanie informacji o windykacji
description: Ten temat objaśnia proces sprawdzania informacji o windykacji, a także różnych opcji konfiguracji i transakcji windykacji.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustCollectionsPool, SysQueryForm, CustCollectionsAgent, OMTeamSelectMemberDialog, CustVendReportInterval, CustParameters, CustAgingSnapshot, CustVendAgingBucketLookUp, CustCollectionsPoolsListPage, CustCollectionsContactPart, CustCollections
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9bbfb6537118a9936c127018427b0516e7ea002a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971535"
---
# <a name="review-collections-information"></a>Przeglądanie informacji o windykacji

[!include [banner](../../includes/banner.md)]

Ten temat objaśnia proces sprawdzania informacji o windykacji, a także różnych opcji konfiguracji i transakcji windykacji. Ta procedura wykorzystuje firmę demonstracyjną USMF.

## <a name="create-customer-pools"></a>Tworzenie pul klientów
1. W okienku nawigacji przejdź do **Moduły > Kredyty i windykacja > Ustawienia > Pule klientów**.
- Na tej stronie można ustawić pule klientów, które są kwerendami definiującymi grupę kont odbiorców, które mogą być wyświetlane i zarządzane dla procesów windykacji lub wiekowania. Używaj pul klientów, aby filtrować informacje na stronie listy **Windykacja** i na powiązanych stronach list. Pule klientów mogą również służyć do filtrowania kont odbiorców, które są uwzględniane podczas tworzenia migawki wiekowania.  
- Pule klientów mogą służyć do filtrowania kont odbiorców, które są uwzględniane podczas tworzenia migawki wiekowania.  
2. Wybierz pozycję **Nowy**.
3. W polu **Identyfikator puli** wpisz wartość.
4. W polu **Opis puli** wpisz wartość.
5. Kliknij opcję **Wybierz kryteria puli.**
6. W polu **Kryteria** wpisz wartość.
7. Kliknij przycisk **OK**.
8. Wybierz **Podgląd puli klientów**.

## <a name="create-collections-agents"></a>Tworzenie agentów ds. windykacji
1. W okienku nawigacji przejdź do **Moduły > Kredyty i windykacja > Ustawienia > Agenci ds. windykacji**.  
- Ta strona służy do ustawiania pracowników jako agentów ds. windykacji i opcjonalnie przypisywania im pul klientów. *Agent ds. windykacji* jest osobą, która współpracuje z odbiorcami w celu upewnienia się, że płatności są inkasowane w terminie.  
- Agenci ds. windykacji skonfigurowani na tej stronie są automatycznie dodawani do zespołu windykacji. Jeśli zespół jest wybrany na stronie **Parametry modułu rozrachunków z odbiorcami** w polu **Zespół**, agenci ds. windykacji zostaną do niego dodani. Jeśli zespół nie został wybrany, nowy zespół o nazwie Windykacja zostanie automatycznie utworzony, a agenci ds. windykacji dodani do niego.  
2. Wybierz żądanego agenta, a następnie wybierz opcję **Dodaj** na stronie.
3. W polu **Identyfikator puli** wybierz odpowiedni rekord z menu rozwijanego.
4. Zaznacz lub wyczyść pole wyboru **Domyślna pula**.
- Zaznacz tę opcję, aby uwzględniać wszystkie pule klientów na listach filtrów dla wybranego agenta ds. windykacji.. Jeśli ta opcja nie jest zaznaczona, na listach filtrów są dostępne tylko pule klientów przypisane do agent ds. windykacji.  

## <a name="create-aging-period-definition"></a>Tworzenie definicji okresu wiekowania
1. W okienku nawigacji przejdź do **Moduły > Kredyty i windykacja > Ustawienia > Definicje okresów wiekowania**.
- Definicje okresów wiekowania można użyć do analizy terminów płatności kont odbiorcy i kont dostawcy na podstawie wprowadzonej daty. Każdy okres wiekowania ustawiony dla definicji okresu wiekowania odpowiada kolumnie na stronie listy lub w formularzu lub raporcie podczas dokonywania analizy.  
2. Wybierz pozycję **Nowy**.
3. W polu **Definicja okresu wiekowania** wpisz wartość.
4. W polu **Opis** wpisz wartość.
- Określ nazwę, jednostkę i zakres dla każdego okresu wiekowania, który ma być uwzględniony w definicji okresu wiekowania. Wiersz, który w polu Jednostka ma wartość zero (0), oznacza datę uruchomienia analizy. Wiersze przed wierszem zerowym będą miały wartość -1, a wiersze za wierszem zerowym będą miały wartość 1 jako domyślny wpis w polu Jednostka, ale można to zmieniać. Wybierz **W górę** i **W dół**, aby zmienić kolejność wierszy. Wiersz 0 (zerowy) nie może być przeniesiony.  
- Umieść wskaźnik w miejscu, w którym ma być wstawiony nowy wiersz, i kliknij przycisk **Dodaj**.  
- Umożliwia wybranie wskaźnika reprezentującego okres wiekowania w formularzu i na stronie listy **Windykacja**. Na przykład można wybrać zielony wskaźnik dla bieżącego okresu, żółty dla okresu 30 dni po dacie i czerwony wskaźnik dla okresu 90 dni po dacie.  
- Służy do wybrania kierunku drukowania dla definicji okresu wiekowania. Wybranie tej opcji określa kolejność wyświetlania kolumn w raportach wiekowania dla odbiorców lub dostawców.  
  - W przód — Drukowanie kolumn w tej samej kolejności, w jakiej nagłówki pojawiają się w tabeli, począwszy od górnego wiersza.  
  - W tył — Drukowanie kolumn w kolejności odwrotnej do tej, w jakiej nagłówki pojawiają się w tabeli, począwszy od dolnego wiersza.    

## <a name="setup-collections-parameters"></a>Konfigurowanie parametrów windykacji
1. W okienku nawigacji przejdź do **Moduły > Kredyty i windykacja > Ustawienia > Parametry modułu rozrachunków z odbiorcami**.
2. Wybierz kartę **Windykacja**
3. Rozwiń lub zwiń sekcję **Ustawienia domyślne windykacji**.
- Wybierz definicję okresu wiekowania dla domyślnej migawki wiekowania, która będzie używana w formularzu **Windykacja**.  
- Zaznacz zespół, do którego agenci ds. windykacji są przypisani w formularzu **Agent ds. windykacji**. Na liście są wyświetlane tylko zespoły, które mają typ zespołu Windykacja.  
4. Rozwiń lub zwiń sekcję **Odpisz**.
- Wybierz arkusz skonfigurowany jako codzienny arkuszy księgi, który ma być używany podczas odpisywania transakcji za pomocą formularza **Windykacja** lub pokrewnych stron list.  
- Wybierz domyślny kod przyczyny używany podczas tworzenia transakcji odpisu za pomocą formularza **Windykacja** lub powiązanych stron list.  
- Wybierz tę opcję, aby utworzyć osobny wiersz arkusza dla kwoty podatku od sprzedaży podczas tworzenia transakcji odpisu za pomocą strony **Windykacja** lub stron powiązanych list. Jeśli zostanie wybrana ta opcja, można łatwo śledzić kwoty podatku, które wiążą się z transakcjami odpisu. Można śledzić kwoty podatku osobno, co ułatwia dostosowanie zobowiązań z tytułu podatku do określonego okresu.  
5. Rozwiń lub zwiń sekcję **Szablon wiadomości e-mail**.
- Wybierz szablon wiadomości e-mail, który ma być używany przy wysyłaniu wiadomości e-mail przy użyciu akcji **E-mail > Transakcje** wymagające kontaktu dostępnej w formularzu **Windykacja**.  
- Wybierz szablon wiadomości e-mail, który ma być używany przy wysyłaniu wyciągu odbiorcy jako załącznika do wiadomości e-mail przy użyciu akcji **E-mail > Wyciąg wymagający** kontaktu dostępnej w formularzu **Windykacja**.  
- Wybierz szablon wiadomości e-mail, który ma być używany przy wysyłaniu wiadomości e-mail przy użyciu akcji **E-mail > Transakcje** sprzedawcy dostępnej w formularzu **Windykacja**.  

## <a name="age-customer-balance"></a>Wiekowanie salda odbiorcy
1. W okienku nawigacji przejdź do **Moduły > Kredyty i windykacja > Ustawienia > Zadania okresowe > Wiekuj salda odbiorcy**.
- Wybierz definicję okresu wiekowania. Transakcje są wiekowane według okresów wiekowania zdefiniowanych w wybranym okresie wiekowania.  
- Należy wybrać pulę odbiorców lub zostawić to pole puste, by utworzyć migawkę wiekowania dla wszystkich odbiorców.. Jeśli wybrano pulę odbiorców, proces migawki wiekowania jest stosowany tylko do kont odbiorców należących do puli odbiorców. Wybrana pula odbiorców musi być typu Migawka wiekowania.  
- Umożliwia wybór typu daty, na której ma się opierać migawka wiekowania.  
  - Datę transakcji — Wiekowanie każdej transakcję na podstawie jej daty transakcji.    
  - Data wymagalności — Wiekowanie każdej transakcji na podstawie jej terminu płatności.    
  - Data dokumentu — Wiekowanie każdej transakcji na podstawie jej daty dokumentu.  
- Umożliwia wybranie daty jako bieżącej daty dla migawki wiekowania. Okresy wiekowania są obliczane na podstawie tej daty.    
  - Data dzisiejsza — Używanie daty systemowej. Należy wybrać tę opcję, jeśli przetwarzanie ma być realizowane cyklicznie dla zadań wsadowych. Zastosowanie tej daty powoduje, partie cykliczne mogą być okresowo i używana jest wtedy data systemowa.    
  - Wybrana data — Używanie określonej przez siebie daty. Jeśli zostanie wybrana ta opcja, należy wprowadzić datę wiekowania.  
2. Kliknij przycisk **OK**.

## <a name="view-aged-customer-balances"></a>Wyświetlanie wiekowanego salda odbiorcy
1. W okienku nawigacji przejdź do **Moduły > Kredyty i windykacja > Ustawienia > Windykacja > Wiekowane salda**.
- Użyj tej strony listy, aby obejrzeć salda odbiorców i kwoty przeterminowane według okresów wiekowania. Te informacje są przechowywane w migawce wiekowania. Okresy wiekowania są określone przez używaną definicję okresu wiekowania. Definicja okresu wiekowania jest pobierana z puli klientów, o ile została określona dla zapytania o pulę. Jeśli pula klientów nie ma definicji okresu wiekowania, jest używana domyślna definicja okresu wiekowania określona w formularzu Parametry modułu rozrachunków z odbiorcami.  
2. Rozwiń pole informacji **Kontakt**. Tutaj można wyświetlić informacje kontaktowe:
- Osoba kontaktowa dla odbiorcy w sprawie windykacji.  
- Domyślmy sprzedawca dla odbiorcy.  
3. Rozwiń pole informacji **Limit kredytu**.
- Pole informacji **Informacje o kredycie** umożliwia wyświetlenie limit kredytu i bieżącego salda dla odbiorcy.  

## <a name="view-customer-collections-details"></a>Wyświetl szczegółów windykacji od odbiorcy
1. Upewnij się, że wybrano żądany rekord.
2. Rozwiń pola informacyjne **Adresy**, **Kontakt**, **Wiekowanie** i **Limit kredytu**, aby wyświetlić daną informację.
3. W okienku akcji wybierz pozycję **Windykacja**.
- Aktualizacja migawki wiekowania dla odbiorcy przy użyciu bieżącej daty jako daty wiekowania, z którą są porównywane daty transakcji. Jeśli migawka wiekowania zawiera informacje dla wielu firm, zaktualizowana migawka zawiera informacje dla tego samego zestawu firm. Kwoty są przechowywane w walucie rozliczeniowej firmy, w której użytkownik był zalogowany podczas aktualizacji migawki wiekowania.  
- Wybierz definicję okresu wiekowania. Domyślnie jest wyświetlana definicja okresu wiekowania skojarzona z migawką wiekowania dla odbiorcy. Definicja okresu wiekowania decyduje o okresach wiekowania i kwotach, które są wyświetlane w polach informacji **Wiekowane salda** i **Informacje o kredycie**.  
- Otwórz menu następujących opcji:    
  - Firma — Kwoty w polach informacji Wiekowane salda i Informacje o kredycie są wyświetlane w walucie rozliczeniowej firmy.  
  - Odbiorca — Kwoty w polach informacji Wiekowane salda i Informacje o kredycie są wyświetlane w walucie odbiorcy.  
- Wybierz jedną lub więcej firm w migawki wiekowania odbiorcy, dla których mają zostać wyświetlone informacje. Firmy wyświetlane na liście zostały wybrane podczas tworzenia migawki wiekowania.  
- Wyświetlanie zestawienia dla odbiorcy w formacie programu Microsoft Excel. Można wybrać datę początkową zakresu transakcji do uwzględnienia na wyciągu oraz zdecydować, czy mają być uwzględniane tylko otwarte transakcje czy też transakcje otwarte i rozliczone. Jeśli migawka wiekowania zawiera informacje z wielu firm, transakcje zostaną uwzględnione dla nich wszystkich.  
- Otwieranie formularza **Dokumenty**, w którym można tworzyć lub edytować dokumenty i notatki.  
4. W okienku akcji wybierz opcję **Komunikowanie**.  
- Otwieranie programu Outlook, z którego można wysłać wiadomość e-mail do osoby kontaktowej określonej w polu Kontakt. Jeśli osoba kontaktowa ds. windykacji nie jest określona, używany jest adres podstawowy dla odbiorcy. Jeśli kontakt podstawowy nie jest określony, wiadomości e-mail wysyłane są na pierwszy adres wymieniony w formularzu **Kontakty**. Wybrane transakcje zostaną dołączone jako załączniki. Załącznik jest w formacie programu Excel i zawiera trzy arkusze. W formularzu **Parametry modułu rozrachunków z odbiorcami** można określić szablon wiadomości e-mail, który będzie używany dla wiadomości e-mail do osób kontaktowych odbiorcy.  
- Ten przycisk jest niedostępny, jeśli osoba kontaktowa wybrana w tym formularzu nie ma skonfigurowanego adresu e-mail.  
- Przygotowanie zestawienia i otwarcie programu Outlook, z którego można wysłać wiadomość e-mail z załączonym zestawieniem na adres określony w polu **Kontakt**. Jeśli osoba kontaktowa ds. windykacji nie jest określona, używany jest adres podstawowy dla odbiorcy. Jeśli kontakt podstawowy nie jest określony, wiadomości e-mail wysyłane są na pierwszy adres wymieniony w formularzu **Kontakty**.  
- Ten przycisk jest niedostępny, jeśli osoba kontaktowa wybrana w tym formularzu nie ma skonfigurowanego adresu e-mail.  
- Otwarcie programu Outlook, z którego można wysłać wiadomość e-mail do pracownika określonego jako przedstawiciel handlowy w grupie sprzedaży przypisanej do odbiorcy. Jeśli wybrano transakcje, zostaną one dołączone jako załączniki. Załącznik jest w formacie programu Excel i zawiera dwa arkusze. W formularzu **Parametry modułu rozrachunków z odbiorcami** można określić szablon wiadomości e-mail, który będzie używany dla wiadomości e-mail do sprzedawców.  
- Ten przycisk jest niedostępny, jeśli sprzedawca wyświetlany w tym formularzu nie ma skonfigurowanego adresu e-mail.  
- Można wyświetlać transakcje odbiorcy i wykonywać na nich akcje. Jeśli jest używana funkcja płatności scentralizowanych, zostaną uwzględnione informacje dla wszystkich firm objętych migawką wiekowania odbiorcy. Można ograniczyć informacje o firmach, klikając przycisk **Firma** znajdujący się w okienku akcji w grupie **Wybierz**.  
- Zmiana stanu windykacji wybranych transakcji.    
  - Niesporne — Nie miały miejsca żadne działania windykacyjne dla transakcji.    
  - Sporne — Odbiorca powiadomił, że występuje problem z transakcją.    
  - Przyrzeczenie zapłaty — Odbiorca zgodził się zapłacić kwotę transakcji.    
  - Rozwiązane — Wszystkie problemy z transakcją zostały rozwiązane i nie są wymagane żadne dodatkowe czynności windykacyjne.  
- Otwieranie menu, w którym można wybrać jeden z następujących elementów w celu określenia, które transakcje mają być wyświetlane w tym formularzu:    
  - Otwarte — Wyświetlanie tylko transakcji, które nie zostały rozliczone.    
  - Otwarte i zamknięte — Wyświetlanie wszystkich transakcji, zarówno rozliczonych, jak i nierozliczonych.  
- Przetwarzanie wybranych płatności wybranego jako płatności z niewystarczającymi funduszami (NF).    
  - Ten przycisk jest dostępny tylko wtedy, gdy wybrana transakcja jest płatnością (saldem faktury bez faktury) wprowadzoną w arkuszu płatności, konto bankowe jest przypisane do transakcji, a płatność nie została wcześniej anulowana.  
- Odpisywanie wybranych transakcji.  
- Oznaczanie wybranych transakcji do rozliczenia między sobą.  
- Otwieranie formularza **Oryginalny dokument**, w którym można obejrzeć i wydrukować dokument dla wybranej transakcji.  
- Otwórz **menu** następujących opcji:    
  - Windykacja — Wyświetlanie tylko tych działań, które zostały utworzone w formularzu Windykacja.    
  - Wszystko — Wyświetlenie wszystkich działań dla odbiorcy, niezależnie od tego, gdzie te działania zostały utworzone.  
- Otwórz **menu** następujących opcji:    
  - Otwarte — Wyświetlanie tylko tych działań, które nie zostały zamknięte.    
  - Otwarte i zamknięte — Wyświetlenie wszystkich działań, niezależnie od ich stanu.  
- Wybierz sprawę windykacji przypisaną do odbiorcy lub pozostaw to pole puste. W przypadku wybrania sprawy w tym formularzu są wyświetlane tylko transakcje i działania skojarzone z tą sprawą.  
5. Wybierz **Pokaż listę**.
- Wybierz konto odbiorcy lub zaakceptuj wpis domyślny. Domyślnie jest to konto odbiorcy wybrane na stronie listy lub w formularzu, z którego otwarto ten formularz. Jeśli formularz otwarto ze strony listy, odbiorcami na liście są odbiorcy należący do puli windykacji używanej na stronie listy.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]