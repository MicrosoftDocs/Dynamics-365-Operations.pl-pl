---
title: "Omówienie Pomocy"
description: "Ten artykuł zawiera omówienie składników systemu Pomocy programu Microsoft Dynamics 365 for Operations. Wyjaśniono tu również, jak można dostarczać niestandardową dokumentację i szkolenia dla swojej organizacji."
author: margoc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16381
ms.assetid: 018c148c-9cbd-41e0-8186-d75dbf66288f
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 240060606c8a2955c3f0a0d47fb25b0cde64c187
ms.lasthandoff: 03/31/2017


---

# <a name="help-overview"></a>Omówienie Pomocy

Ten artykuł zawiera omówienie składników systemu Pomocy programu Microsoft Dynamics 365 for Operations. Wyjaśniono tu również, jak można dostarczać niestandardową dokumentację i szkolenia dla swojej organizacji. 

Program Dynamics 365 for Operations zawiera system Pomocy oparty na dwóch głównych składnikach:

-   Witryna z dokumentacją
-   Przewodniki po zadaniach

Zarówno artykuły, jak i przewodniki po zadaniach można otworzyć z okienka pomocy w programie Dynamics 365 for Operations, jak przedstawiono na zrzucie ekranu. [![Okienko pomocy](./media/help-pane-ops-task-guides-1024x741.png)](./media/help-pane-ops-task-guides.png) Ten artykuł zawiera opis systemu pomocy oraz wyjaśnia sposób tworzenia niestandardowych dokumentów i materiałów szkoleniowych w danej organizacji.

## <a name="help-on-docsmicrosoftcom"></a>Pomoc w witrynie docs.microsoft.com
Witryna docs.microsoft.com ([docs.microsoft.com/dynamics365/operations](https://docs.microsoft.com/en-us/dynamics365/#pivot=solutions&panel=solutions_operations) to podstawowe źródło dokumentacji produktu Dynamics 365 for Operations. Witryna oferuje następujące funkcje:

-   **Dostęp do najaktualniejszych treści** — Witryna pozwala szybciej i elastyczniej tworzyć, dostarczać i aktualizować dokumentację produktu. To pomaga zagwarantować, że użytkownik ma dostęp do najnowszych informacji technicznych.
-    **Artykuły pisane przez ekspertów** — Witryna zawiera bardziej rozbudowany zestaw dokumentacji produktu, który może być rozszerzany przez członków społeczności wewnątrz i na zewnątrz firmy Microsoft.
-   ** Dostęp do różnych typów zawartości** — Witryna umożliwia szybki dostęp do różnych rodzajów treści o programie Dynamics 365 for Operations, takich jak prezentacje Microsoft Office Mix, przewodniki po zadaniach, filmy i artykuły wiki.
-    **Zawartość, która pomaga w obsłudze procesów biznesowych** — Witryna zawiera treści skoncentrowane na procesach biznesowych, które korzystają z narzędzia do modelowania procesów biznesowych (BPM) dostępnego w usłudze Microsoft Dynamics Lifecycle Services (LCS).

Wszystkie treści przenieśliśmy ze stron wiki Pomocy do dokumentów. Jesteśmy bardzo zadowoleni z nowej wersji witryny i mamy nadzieję, że klienci również będą.

### <a name="when-can-we-use-it"></a>Kiedy można korzystać?

Już teraz można czytać zawartość dokumentów — materiały są publicznie dostępne i można je przeszukiwać bez konieczności zalogowania się. Do wyszukiwania materiałów możesz używać dowolnej wyszukiwarki. Jeśli chcesz, możesz komentować artykuły w witrynie, logując się za pomocą konta GitHub.


## <a name="task-guides"></a>Przewodniki po zadaniach
Przewodniki po zadaniach oferują interaktywne prezentacje poszczególnych kroków w zadaniach i procesach biznesowych. Przewodnik można otworzyć (i odtworzyć) z okienka pomocy. Po kliknięciu przewodnika po zadaniu okienko pomocy pokaże dokładne instrukcje wykonania zadania. Dostępne są przetłumaczone przewodniki po zadaniach. [![Przewodnik po zadaniu w widoku do czytania](./media/task-guide-ops-1024x742.png)](./media/task-guide-ops.png) Aby rozpocząć korzystanie z interaktywnego przewodnika, kliknij opcję **Uruchom przewodnik po zadaniach** u dołu okienka pomocy. Zostanie wyświetlony czarny wskaźnik pokazujący zadanie, które ma być wykonane. Postępuj zgodnie z instrukcjami wyświetlanymi w interfejsie użytkownika, a następnie wprowadź dane, zgodnie ze wskazówkami. [![Instrukcje krok po kroku w przewodniku po zadaniu](./media/task-guide-step-1-ops.png)](./media/task-guide-step-1-ops.png) **Ważne:** Dane wprowadzone podczas odtwarzania przewodnika po zadaniu są realne. Jeśli pracujesz w środowisku produkcyjnym, dane zostaną wprowadzone w firmie, która jest aktualnie używana.

### <a name="it-all-begins-with-task-recorder"></a>Wszystko zaczyna się w rejestratorze zadań

Przewodniki po zadaniach są tworzone przy użyciu rejestratora zadań. Jeśli korzystasz z Rejestratora zadań, wszystkie czynności wykonywane w interfejsie użytkownika programu Dynamics 365 for Operations (takie jak klikanie menu, zmienianie ustawień i wprowadzanie danych) są nagrywane. Zapisywane kroki są zbiorczo zwane nagraniami zadań. Jak zostało wyjaśnione w poprzedniej sekcji, rejestry zadań można wyświetlić w okienku pomocy i odtworzyć jako przewodniki po zadaniach. Istnieją inne sposoby używania nagrań zadań:

-   **Zapisywanie nagrań zadań w BPM** — można zapisać nagranie zadania w wierszu hierarchii biblioteki BPM w LCS. Po zapisaniu nagrania zadania w BPM zostanie wygenerowany i wyświetlony diagram blokowy wraz z krokami nagrania. **Uwaga:** Aby wyświetlić nagranie zadania okienku pomocy w programie Dynamics 365 for Operations i odtworzyć je jako przewodnik po zadaniu, należy zapisać nagranie w bibliotece BPM.
-   **Zapisywanie nagrań zadań w formie dokumentów programu Word** — zapisując nagranie zadania jako dokument programu Microsoft Word, można łatwo tworzyć przewodniki szkoleniowych nadające się do drukowania.

Aby uzyskać więcej informacji na temat Rejestratora zadań, zobacz [Rejestrator zadań w programie Dynamics 365 for Operations](../user-interface/task-recorder.md).

### <a name="creating-customized-task-recordings"></a>Tworzenie niestandardowych nagrań zadań

Można utworzyć własne nagrania zadań lub pobierać i dostosowywać nagrania zadań oferowane przez Microsoft. W związku z tym można utworzyć dostosowaną Pomoc dla organizacji, która odpowiada określonej implementacji programu Dynamics 365 for Operations. Aby wyświetlić nagranie zadania w okienku pomocy w programie Dynamics 365 for Operations i odtworzyć je jako przewodnik po zadaniu, należy zapisać nagranie w bibliotece BPM w usłudze LCS. Jeśli jesteś partnerem i podwyższasz status biblioteki do biblioteki firmowej oraz dołączasz ją do rozwiązania, będzie ona dostępna dla Twoich klientów. Aby uzyskać pełne instrukcje, zobacz [Używanie nagrań zadań do tworzenia dokumentacji i szkoleń](../user-interface/task-recorder.md).

## <a name="in-product-help"></a>Pomoc w produkcie
Aby uzyskać dostęp do zawartości pomocy w programie Dynamics 365 for Operations, kliknij ikonę **pomocy** (**?**), a następnie wybierz polecenie Pomoc lub naciśnij klawisze Ctrl + Shift +?. W obu przypadkach zostanie otwarte okienko pomocy. Z okienka pomocy można uzyskać dostęp do artykułów lub przewodników po zadaniach. [![](./media/help-pane-wiki-1024x684.png)](./media/help-pane-wiki.png)

### <a name="accessing-articles-from-the-help-pane"></a>Uzyskiwanie dostępu do artykułów z okienka Pomocy

Z okienka pomocy można uzyskać dostęp artykułów mających zastosowanie do klienta programu Dynamics 365 for Operations. Gdy po raz pierwszy otworzysz okienko pomocy i klikniesz kartę **Wiki**, zobaczysz artykuły mające zastosowanie do strony aktualnie wyświetlonej w programie Dynamics 365 for Operations. Jeśli nie zostaną znalezione żadne artykuły, możesz wprowadzić słowa kluczowe, aby doprecyzować wyszukiwanie. Po kliknięciu artykułu w okienku pomocy w przeglądarce zostanie otwarta nowa karta z artykułem. 

### <a name="accessing-task-guides-from-the-help-pane"></a>Uzyskiwanie dostępu do przewodników po zadaniach z okienka Pomocy

Zanim będzie można uzyskać dostęp do przewodników po zadaniach z okienka pomocy, administrator systemu musi przejść do strony **Parametry systemu** w programie Dynamics 365 for Operations i skonfigurować niektóre ustawienia. **Uwagi:**

-   Aby skonfigurować pomoc, musisz się zalogować przy użyciu konta w tej samej dzierżawie, w której jest wdrożony program Dynamics 365 for Operations.
-   Nie jest możliwe nawiązanie połączenia z biblioteką LCS z wystąpienia programu Dynamics 365 for Operations działającego na lokalnym wirtualnym dysku twardym (VHD).

[![Formularz Parametry systemowe z ustawieniami Pomocy](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) Na stronie **Parametry systemowe** wykonaj następujące czynności:

1.  **Ważne: **Podczas pierwszego otwierania karty Pomoc należy utworzyć połączenie z usługami Lifecycle Services. Kliknij łącze na środku formularza, poczekaj na nawiązanie połączenia, zamknij okno dialogowe i kliknij przycisk OK, co spowoduje przejście do formularza Parametry.[![Łączenie z usługą LCS](./media/connect-to-lcs-crop-1024x365.png)](./media/connect-to-lcs-crop.png)
2.  Wybierz projekt Lifecycle Services, z którym chcesz się połączyć.
3.  Wybierz biblioteki BPM (w ramach wybranego projektu), z których będą pobierane nagrania zadań.
4.  Ustaw kolejność wyświetlania bibliotek BPM. Określa kolejność wyświetlania nagrań z bibliotek w okienku pomocy.

Po wykonaniu tych kroków przez administratora systemu można otworzyć okienko pomocy i kliknąć kartę **Przewodniki po zadaniach**. Teraz widać przewodniki po zadaniach, które mają zastosowanie do strony aktualnie wyświetlanej w programie Dynamics 365 for Operations. Jeśli nie zostaną znalezione żadne przewodniki po zadaniach, możesz wprowadzić słowa kluczowe, aby doprecyzować wyszukiwanie. Po kliknięciu przewodnika po zadaniu w okienku pomocy zobaczysz w nim instrukcje krok po kroku i można odtworzyć przewodnik po zadaniu. [![Przewodnik po zadaniu w widoku do czytania](./media/task-guide-ops-1024x742.png)](./media/task-guide-ops.png)

### <a name="where-are-the-translated-task-guides"></a>Gdzie są przetłumaczone przewodniki po zadaniach?

Przetłumaczone przewodniki po zadaniach są wydawane w bibliotekach z tytułem zawierającym wyrażenie „Wszystkie języki”. Aby wyświetlić przetłumaczone przewodniki po zadaniach w pomocy w programie Dynamics 365 for Operations, upewnij się, że masz połączenie z odpowiednią biblioteką. Język wyświetlania przetłumaczonego przewodnika po zadaniu jest kontrolowany przez każdego użytkownika w ustawieniach języka w oknie **Opcje** &gt; **Preferencje**. 
-   Jeśli przewodnik po zadaniu został przetłumaczony, po otwarciu przewodnika jego cały tekst będzie wyświetlany w wybranym języku.
-   Jeśli przewodnik po zadaniu nie został jeszcze przetłumaczony, po otwarciu przewodnika tylko część tekstu (formanty) będzie wyświetlana w wybranym języku.

## <a name="additional-resources"></a>Dodatkowe zasoby
W poniższej tabeli wymieniono witryny sieci Web, które dostarczają zawartość programu Dynamics 365 for Operations. Nasze strony z zawartością są zorganizowane tak, aby wspomagać cykl życia klienta. Do każdej fazy jest inny zestaw witryn. Witryny z gwiazdką (\*) obok nazwy wymagają logowania przy użyciu konta, które jest skojarzone z planem usługi.

| Oddział                                                                     | opis                                                                                                                                                                                                                                |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Docs.microsoft.com](https://docs.microsoft.com/en-us/dynamics365/#pivot=solutions&panel=solutions_operations) | Hosty lub łącza do dokumentacji wszystkich produktów dla programu Dynamics 365 for Operations.                                                                                                                                                               |
| [Usługa Lifecycle Services](http://lcs.dynamics.com/en/)\*                      | Zawiera obszar współpracy oparty na chmurze, w którym klienci i ich partnerzy mogą całościowo zarządzać projektami w programie Dynamics 365 for Operations — od przedsprzedaży po wdrożenie i bieżącą eksploatację. Ta witryna jest przydatna we wszystkich fazach implementacji. |
| [CustomerSource](http://www.customersource.com/)\*                       | Zawiera rozbudowane zasoby szkoleniowe i jest główną witryną pomocy technicznej dla programu Dynamics 365 for Operations. Dostęp do określonych zasobów w witrynie może wymagać zalogowania się.                                                                      |
| [Blog pomocy technicznej](http://aka.ms/AXSupportBlog)                              | Zawiera porady i wskazówki publikowane przez zespół pomocy technicznej programu Dynamics 365 for Operations.                                                                                                                                                  |
| [MSDN](http://aka.ms/AXMSDN)                                             | Obsługuje zawartość z poprzednich wersji przeznaczoną dla deweloperów.                                                                                                                                                                       |
| [TechNet](http://aka.ms/TechNet)                                         | Obsługuje zawartość z poprzednich wersji przeznaczoną dla informatyków i użytkowników aplikacji.                                                                                                                                           |
| [Społeczność Dynamics](http://community.dynamics.com/en/)                  | Obsługuje blogi, fora i wideo.                                                                                                                                                                                                           |
| [Microsoft.com/Dynamics/](http://www.microsoft.com/dynamics/)                 | Zawiera ocenę i informacje o sprzedaży.                                                                                                                                                                                                 |



<a name="see-also"></a>Informacje dodatkowe
--------

[System Pomocy programu Dynamics 365 for Operations (arkusz informacyjny do pobrania)](https://mbs.microsoft.com/files/public/CS/AX2012R3/DynamicsAXHelpSystemFactSheet.pdf)

[Rejestrator zadań w programie Microsoft Dynamics 365 for Operations](../user-interface/task-recorder.md)

[Tworzenie dokumentacji lub szkolenia przy użyciu nagrań zadań](../user-interface/task-recorder.md)

[Nowe lub zaktualizowane przewodniki po zadaniach (listopad 2016 r.)](new-task-guides-november-2016.md)
[Nowe lub zaktualizowane przewodniki po zadaniach (sierpień 2016 r.)](new-updated-task-guides-available-august-2016.md)
[Nowe lub zaktualizowane przewodniki po zadaniach (maj 2016 r.)](new-updated-task-guides-available-may-2016.md)
[Nowe przewodniki po zadaniach (luty 2016 r.)](new-task-guides-available-february-2016.md)






