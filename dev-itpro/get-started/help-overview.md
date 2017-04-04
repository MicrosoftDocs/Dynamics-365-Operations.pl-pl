---
title: "Omówienie pomocy"
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

# <a name="help-overview"></a>Omówienie pomocy

Ten artykuł zawiera omówienie składników systemu Pomocy programu Microsoft Dynamics 365 for Operations. Wyjaśniono tu również, jak można dostarczać niestandardową dokumentację i szkolenia dla swojej organizacji. 

Program Dynamics 365 for Operations zawiera system Pomocy oparty na dwóch głównych składnikach:

-   Witryna dokumentacji
-   Przewodniki po zadaniach

Możesz uzyskać dostęp zarówno artykuły prowadnice zadania z okienka Pomocy w usłudze Dynamics 365 dla operacji jak pokazano na poniższej ilustracji. [![Okienko Pomoc](./media/help-pane-ops-task-guides-1024x741.png)](./media/help-pane-ops-task-guides.png) w tym artykule opisano systemu pomocy i wyjaśnia, w jaki sposób tworzenia niestandardowych dokumentację i materiały szkoleniowe dla danej organizacji.

## <a name="help-on-docsmicrosoftcom"></a>Pomoc na temat docs.microsoft.com
Witryna docs.microsoft.com ([docs.microsoft.com/dynamics365/operations](https://docs.microsoft.com/en-us/dynamics365/#pivot=solutions&panel=solutions_operations) jest podstawowym źródłem 365 Dynamics dla operacji w dokumentacji produktu. Witryna oferuje następujące funkcje:

-   **Dostęp do najbardziej aktualnej zawartości** — witryna daje szybsze i bardziej elastyczny sposób tworzenia, dostarczania i aktualizacji dokumentacji produktu. To pomaga zagwarantować, że użytkownik ma dostęp do najnowszych informacji technicznych.
-    **Zawartość, która jest napisane przez ekspertów** — witryna zawiera bogatszy zestaw dokumentacji produktu, który może zostać zwiększone przez członków społeczności wewnątrz i na zewnątrz firmy Microsoft.
-   ** Dostęp do różnych typów zawartości ** – witryna umożliwia w szybkie dostępu do różnych typów zawartości o 365 Dynamics dla operacji, takich jak Microsoft Office Mix prezentacje, zadanie przewodniki, filmy wideo i artykułów wiki.
-    **Zawartość, która obsługuje procesy biznesowe** — strona zawiera koncentruje się proces zawartości biznesowej, który wykorzystuje narzędzie do modelowania procesami biznesowymi (BPM) w Microsoft Dynamics cyklu życia usługi (LCS).

Mamy już migracji całej zawartości z naszych poprzednich wiki pomocy do dokumentów. Cieszymy o naszej nowej witryny i mam nadzieję, że będzie zbyt.

### <a name="when-can-we-use-it"></a>Kiedy można korzystać?

Możesz przeczytać zawartość na dokumenty już teraz — jest w pełni publicznych i można je przeszukiwać bez konieczności logowania. Do wyszukiwania materiałów możesz używać dowolnej wyszukiwarki. Jeśli zostanie wybrana opcja, logując się za pomocą konta GitHub mogą komentować artykułów w witrynie.


## <a name="task-guides"></a>Przewodniki po zadaniach
Przewodnik zadania jest kontrolowanych, z przewodnikiem, interaktywny interfejs, który poprowadzi Cię przez kroki zadania lub procesu biznesowego. Przewodnik (odtwarzanie) zadania można otworzyć z okienka Pomocy. Po pierwszym kliknięciu przewodnik zadań, okienko pomocy pokaże instrukcje krok po kroku dla zadania. Zlokalizowane prowadnice zadania są teraz dostępne. [![Przewodnik zadania widoku czytania](./media/task-guide-ops-1024x742.png)](./media/task-guide-ops.png) aby rozpocząć z przewodnikiem, interaktywny interfejs, kliknij przycisk **zadanie Przewodnik po** w dolnej części okienka Pomocy. Zostanie wyświetlony czarny wskaźnik pokazujący zadanie, które ma być wykonane. Postępuj zgodnie z instrukcjami wyświetlanymi w interfejsie użytkownika, a następnie wprowadź dane, zgodnie ze wskazówkami. [![Zadanie Podręcznik krok instrukcja](./media/task-guide-step-1-ops.png)](./media/task-guide-step-1-ops.png)**ważne:** danych, które należy wprowadzić podczas odtwarzania przewodnik zadania jest prawdziwe. Jeśli pracujesz w środowisku produkcyjnym, dane zostaną wprowadzone w firmie, która jest aktualnie używana.

### <a name="it-all-begins-with-task-recorder"></a>Wszystko zaczyna się w rejestratorze zadań

Przewodniki po zadaniach są tworzone przy użyciu rejestratora zadań. Jeśli korzystasz z Rejestratora zadań, wszystkie czynności wykonywane w interfejsie użytkownika programu Dynamics 365 for Operations (takie jak klikanie menu, zmienianie ustawień i wprowadzanie danych) są nagrywane. Zapisywane kroki są zbiorczo zwane nagraniami zadań. Jak zostało wyjaśnione w poprzedniej sekcji, rejestry zadań można wyświetlić w okienku pomocy i odtworzyć jako przewodniki po zadaniach. Istnieją inne sposoby używania nagrań zadań:

-   **Zapisywanie nagrań zadań w BPM** — można zapisać nagranie zadania w wierszu hierarchii biblioteki BPM w LCS. Po zapisaniu nagrania zadania w BPM zostanie wygenerowany i wyświetlony diagram blokowy wraz z krokami nagrania. **Uwaga:** Aby wyświetlić nagranie zadania okienku pomocy w programie Dynamics 365 for Operations i odtworzyć je jako przewodnik po zadaniu, należy zapisać nagranie w bibliotece BPM.
-   **Zapisywanie nagrań zadań w formie dokumentów programu Word** — zapisując nagranie zadania jako dokument programu Microsoft Word, można łatwo tworzyć przewodniki szkoleniowych nadające się do drukowania.

Aby uzyskać więcej informacji na temat programu Task Recorder, zobacz [Rejestrator zadań w usłudze Dynamics 365 dla operacji](../user-interface/task-recorder.md).

### <a name="creating-customized-task-recordings"></a>Tworzenie niestandardowych nagrań zadań

Można utworzyć własne nagrania zadań lub pobierać i dostosowywać nagrania zadań oferowane przez Microsoft. W związku z tym można utworzyć dostosowaną Pomoc dla organizacji, która odpowiada określonej implementacji programu Dynamics 365 for Operations. Aby wyświetlić zadanie rejestrowania w usłudze Dynamics 365 dla okienka Pomocy operacji i odtworzyć ją jako przewodnik zadania, musisz zapisać nagranie w bibliotece BPM w LCS. Jeśli jesteś naszym partnerem i promowania biblioteki do biblioteki firmy i dołączyć go do rozwiązania, będzie dostępny dla klientów. Aby uzyskać pełne instrukcje, zobacz [za pomocą nagrań zadań do tworzenia dokumentacji lub szkolenia](../user-interface/task-recorder.md).

## <a name="in-product-help"></a>Pomoc w produkcie
Aby uzyskać dostęp do zawartości pomocy w ramach usługi Dynamics 365 dla operacji, kliknij przycisk **Pomoc** (**?**) ikonę i wybierz polecenie Pomoc lub naciśnij klawisze Ctrl + Shift +?. W obu przypadkach zostanie otwarte okienko pomocy. Z okienka Pomocy mogą otwierać artykułów lub prowadnic zadania. [![](./media/help-pane-wiki-1024x684.png)](./media/help-pane-wiki.png)

### <a name="accessing-articles-from-the-help-pane"></a>Dostęp do artykułów z okienka Pomocy

Z okienka Pomocy można dostęp do artykułów, które mają zastosowanie do 365 Dynamics dla operacji klienta. Kiedy najpierw otworzyć okienko pomocy i kliknij przycisk **Wiki** kartę, zobaczysz tych artykułów, które mają zastosowanie do strony, która obecnie jesteś w usłudze Dynamics 365 dla operacji. Jeśli zostaną znalezione nie artykuły, można wprowadzić słowa kluczowe, aby uściślić wyszukiwanie. Po kliknięciu artykuł w okienku Pomoc, Nowa karta zostanie otwarty w przeglądarce i wyświetla ten artykuł. 

### <a name="accessing-task-guides-from-the-help-pane"></a>Dostęp do przewodników zadania z okienka Pomocy

Zanim zadanie prowadnic można uzyskać dostęp z okienka Pomocy, administrator systemu musi przejść do **parametrów systemu** strony w usłudze Dynamics 365 dla operacji i skonfigurowania niektórych ustawień. **Uwagi:**

-   Aby skonfigurować pomoc, musisz się zalogować przy użyciu konta w tej samej dzierżawie, w której jest wdrożony program Dynamics 365 for Operations.
-   Nie jest możliwe nawiązanie połączenia z biblioteką LCS z wystąpienia programu Dynamics 365 for Operations działającego na lokalnym wirtualnym dysku twardym (VHD).

[![Formularz Parametry systemu z ustawieniami pomocy](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) na **parametrów systemu** strony, wykonaj następujące kroki:

1.  **Ważne: **Podczas pierwszego otwierania karty Pomoc należy utworzyć połączenie z usługami Lifecycle Services. Pamiętaj kliknąć łącze w środku formularza, czekać na połączenie, zamknij okno dialogowe i kliknij przycisk OK, aby przejść do formularza Parametry. [![Nawiązać LCS](./media/connect-to-lcs-crop-1024x365.png)](./media/connect-to-lcs-crop.png)
2.  Wybierz projekt Lifecycle Services, z którym chcesz się połączyć.
3.  Wybierz biblioteki BPM (w ramach wybranego projektu), z których będą pobierane nagrania zadań.
4.  Ustaw kolejność wyświetlania bibliotek BPM. Określa kolejność wyświetlania nagrań z bibliotek w okienku pomocy.

Po wykonaniu tych kroków przez administratora systemu można otworzyć okienko pomocy i kliknąć kartę **Przewodniki po zadaniach**. Teraz pojawi się prowadnice zadania, które mają zastosowanie do strony, która obecnie jesteś w usłudze Dynamics 365 dla operacji. Jeśli zostaną znalezione żadne linie zadanie, można wprowadzić słowa kluczowe, aby uściślić wyszukiwanie. Po kliknięciu przycisku Przewodnik zadania w okienku Pomoc okienka Pomocy zawiera instrukcje krok po kroku, a można odtwarzać przewodnik zadania. [![Przewodnik zadania widoku do czytania](./media/task-guide-ops-1024x742.png)](./media/task-guide-ops.png)

### <a name="where-are-the-translated-task-guides"></a>Gdzie są tłumaczone prowadnice zadań?

Tłumaczone prowadnice są zwalniane w bibliotekach z "Wszystkie języki" w tytule zadania. W usłudze Dynamics 365 dla operacji aby w podręczniku zlokalizowane zadań Pomoc, upewnij się, że nawiązano do biblioteki apppropriate. Język, w którym przewodnik zadanie zostanie wyświetlone w steruje dla każdego użytkownika, ustawienia języka w obszarze **opcje**&gt;**preferencje**. 
-   Jeśli przewodnik zadania został przetłumaczony, po otwarciu przewodnika tego zadania, zostanie wyświetlony cały tekst przewodnika zadań w wybranym języku.
-   Jeśli przewodnik zadania nie jeszcze została przetłumaczona, po jego otwarciu, tylko część tekstu (tekst formanty) pojawią się w wybranym języku.

## <a name="additional-resources"></a>Dodatkowe zasoby
W poniższej tabeli wymieniono witryny sieci Web, które dostarczają zawartość programu Dynamics 365 for Operations. Nasze strony z zawartością są zorganizowane tak, aby wspomagać cykl życia klienta. Do każdej fazy jest inny zestaw witryn. Lokacje, które mają znak gwiazdki (\*) obok nazwy wymagają zalogowania się przy użyciu konta, które jest skojarzone z planem usługi.

| Oddział                                                                     | opis                                                                                                                                                                                                                                |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Docs.microsoft.com](https://docs.microsoft.com/en-us/dynamics365/#pivot=solutions&panel=solutions_operations) | Hosty lub łącza do dokumentacji wszystkich produktów dla programu Dynamics 365 for Operations.                                                                                                                                                               |
| [Lifecycle Services](http://lcs.dynamics.com/en/)\*                      | Zawiera obszar współpracy oparty na chmurze, w którym klienci i ich partnerzy mogą całościowo zarządzać projektami w programie Dynamics 365 for Operations — od przedsprzedaży po wdrożenie i bieżącą eksploatację. Ta witryna jest przydatna we wszystkich fazach implementacji. |
| [CustomerSource](http://www.customersource.com/)\*                       | Zawiera rozbudowane zasoby szkoleniowe i jest główną witryną pomocy technicznej dla programu Dynamics 365 for Operations. Dostęp do określonych zasobów w witrynie może wymagać zalogowania się.                                                                      |
| [Pomocy technicznej](http://aka.ms/AXSupportBlog)                              | Zawiera porady i wskazówki publikowane przez zespół pomocy technicznej programu Dynamics 365 for Operations.                                                                                                                                                  |
| [MSDN](http://aka.ms/AXMSDN)                                             | Obsługuje zawartość z poprzednich wersji przeznaczoną dla deweloperów.                                                                                                                                                                       |
| [TechNet](http://aka.ms/TechNet)                                         | Obsługuje zawartość z poprzednich wersji przeznaczoną dla informatyków i użytkowników aplikacji.                                                                                                                                           |
| [Wspólnoty systemu Dynamics](http://community.dynamics.com/en/)                  | Obsługuje blogi, fora i wideo.                                                                                                                                                                                                           |
| [Microsoft.com/Dynamics/](http://www.microsoft.com/dynamics/)                 | Zawiera ocenę i informacje o sprzedaży.                                                                                                                                                                                                 |



<a name="see-also"></a>Informacje dodatkowe
--------

[Pomoc Dynamics 365 dla operacji systemu (do pobrania zestawienie)](https://mbs.microsoft.com/files/public/CS/AX2012R3/DynamicsAXHelpSystemFactSheet.pdf)

[Program Task Recorder w systemie Microsoft Dynamics 365 dla operacji](../user-interface/task-recorder.md)

[Tworzenie dokumentacji lub szkolenia przy użyciu nagrań zadań](../user-interface/task-recorder.md)

[Nowe lub zaktualizowane zadania prowadzi (listopad 2016)](new-task-guides-november-2016.md)<ph id="t1">
</ph>[nowe lub zaktualizowane zadanie prowadzi (sierpień 2016)](new-updated-task-guides-available-august-2016.md)<ph id="t2">
</ph>[nowe lub zaktualizowane zadanie prowadzi (maja 2016)](new-updated-task-guides-available-may-2016.md)<ph id="t3">
</ph>[nowe zadanie prowadzi (luty 2016)](new-task-guides-available-february-2016.md)






