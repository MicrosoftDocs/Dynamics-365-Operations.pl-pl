---
title: Utwórz nowy projekt
description: Ten temat zawiera informacje o metodach tworzenia nowego projektu.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c8c52b8c1c86ea2f6e03cf439ba5930f1006ab4f
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760633"
---
# <a name="create-a-new-project"></a>Utwórz nowy projekt

[!include [banner](../includes/banner.md)]

Aby utworzyć nowy projekt należy wykonać następujące kroki.

1. Na stronie **Zarządzanie projektem** wybierz opcję **Nowy projekt** i wprowadź następujące wartości:

    - **Typ projektu:** Czas i materiały
    - **Nazwa projektu:** Uaktualnianie XYZ faza 2
    - **Grupa projektów:** TM\_WIP
    - **Identyfikator umowy dotyczącej projektu:** 00000002

2. Wybierz opcję **Utwórz projekt**.

## <a name="assign-a-resource-to-a-project"></a>Przypisywanie zasobu do projektu

1. Na stronie **Pracownicy** na liście **Pracownicy** wybierz rekord pracownika, dla którego skonfigurowano wcześniej kompetencje, i otwórz ten rekord.
2. W okienku akcji na karcie **Projekt** w grupie **Ustawienia** wybierz opcję **Przypisz projekty**.
3. Na stronie **Przypisania projektu weryfikacji zasobów**, na karcie **Projekty**, w polu **Dodaj projekt do wybranych projektów** odfiltruj projekt **Uaktualnianie XYZ faza 2**.
4. W okienku **Pozostałe projekty** wybierz projekt, a następnie wybierz przycisk strzałki, aby dodać go do okienka **Wybrane projekty**.

Można również przypisać kategorie do zasobu według potrzeb. Typem kategorii jest **Koszt** lub **Przychód**. Typ kategorii jest określany przez organizację. Jeśli zasób nie ma przypisanych żadnych kategorii, Finance wyszuka domyślną kategorię cen godzinowych dla kosztów i przychodów.

## <a name="set-up-project-resource-and-role-characteristics"></a>Konfigurowanie cech zasobów i ról w projekcie

Kierownik projektu może za pomocą funkcji organizowania zasobów projektu utworzyć role wymagane w projekcie. Ról można używać, jeżeli potwierdzone zasoby są nadal nieznane podczas rezerwowania zasobów. Role mogą służyć do tymczasowego rezerwowania planowanych zasobów, tak aby można było kontynuować etapy planowania projektu.

[![Przykład roli](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg) 

**Scenariusz:** Firma Contoso została wynajęta do wykonania projektu rozliczanego według czasu i materiałów mającego zatwierdzony statut projektu. Młodszy kierownik projektu nadal opracowuje zakres projektu. Menedżer zasobów obecnie identyfikuje konkretne zasoby, które zostaną zarezerwowane do pracy nad nowym projektem. Ze względu na krytyczny charakter projektu jedną z ról wnioskowanych przez sponsora projektu jest starszy kierownik projektu. Menedżer zasobów musi pozyskać nowy zasób oraz zdefiniować rolę w systemie na wypadek, gdyby młodszy kierownik projektu potrzebował informacji o zasobie podczas planowania projektu.

Poniższe kroki pokazują, jak menedżer zasobów może skonfigurować rolę starszego kierownika projektu i skojarzyć z nią cechy zasobu. Później rola może służyć do wyszukiwania dostępnych zasobów posiadających wymagane kompetencje.

1. Na stronie **Konfiguruj role** wybierz opcję **Nowa** i wprowadź następujące wartości:

    - **Identyfikator roli:** Starszy kierownik projektu
    - **Opis:** Starszy kierownik projektu

2. Wybierz opcję **Utwórz**.
3. Wybierz rolę **Starszy kierownik projektu** i wybierz przycisk **Konfiguruj charakterystyki**.
4. W polu **Typ charakterystyki** zaznacz opcję **Umiejętności**.
5. W polu **Dostępne charakterystyki** wprowadź umiejętność, której chcesz poszukać.
6. W polu **Typ charakterystyki** zaznacz opcję **Certyfikat**.
7. W polu **Dostępne charakterystyki** wprowadź typ zaświadczenia, którego chcesz poszukać.

## <a name="assign-a-project-resource-to-a-project"></a>Przypisywanie zasobu projektu do projektu

1. Na stronie **Wszystkie projekty** wybierz projekt **Uaktualnianie XYZ faza 2**.
2. Na karcie **Zespół projektu i planowanie** wybierz przycisk **Dodaj**.
3. W polu **Rola** zaznacz opcję **Członek zespołu**.
4. Wybierz opcję **Rezerwuj z kalendarza**.
5. Na stronie **Dostępność zasobów** wybierz opcję **Ustawienia widoku**.
6. Na stronie **Dostosuj ustawienia widoku** wprowadź następujące wartości:

    - **Format widoku zakresu dat:** Dzień
    - **Wyświetl opisy dostępności:** Tak
    - **Wyświetlanie pozostałych zdolności produkcyjnych:** Tak

7. Na liście zasobów zaznacz zasób.
8. Wybierz opcję **Rezerwacje ostateczne** i **Pełne zdolności produkcyjne**.

## <a name="assign-a-resource-to-a-default-role"></a>Przypisywanie zasobu do roli domyślnej

Aby ułatwić pracę kierownikom projektów lub menedżerom zasobów, można przejść do dokładniejszych ustawień zasobów rezerwowanych dla projektu. Można skojarzyć domyślną rolę z istniejącym zasobem lub nowo pozyskanym zasobem. Na przykład kiedy Daniel był zatrudniany, miał doświadczenie i umiejętności niezbędne do roli analityka biznesowego. Menedżer zasobów przypisał tę rolę jako domyślną rolę Daniela. W związku z tym menedżer zasobów dodał Daniela do puli analityków biznesowych, którzy są dostępni do pracy w projektach.

Podczas rezerwowania zasobów kierownicy projektów mogą filtrować zasoby z rolami dostępne do pracy w projektach. Mogą wykorzystywać te informacje jako jedno z kryteriów wielowątkowej analizy decyzyjnej podczas rozdzielania zasobów. Mogą również dodać inne cechy zasobów do filtra w celu wyszukiwania zasobów, które mają określone umiejętności, wykształcenie i doświadczenie dla danego projektu.

**Scenariusz:** Rozpoczął się zatwierdzony projekt, a na etapie planowania projektu rola starszego kierownika projektu została zarezerwowana jako planowany zasób. Menedżer zasobów pozyskał zasób mogący wypełniać rolę starszego kierownika projektu.

1. Na stronie **Lista zasobów** zaznacz pozycję **Daniel Goldschmidt**.
2. Na stronie **Rola zasobu** wybierz opcję **Nowa** i wprowadź następujące wartości:

    - **Data wprowadzenia:** Wprowadź bieżącą datę.
    - **Data wygaśnięcia:** Wprowadź tekst **Nigdy**.
    - **Rola:** Wprowadź **Starszy kierownik projektu**.

3. Wybierz przycisk **Zapisz** i zamknij stronę.
4. Na karcie **Kompetencje** dodaj umiejętność **ProjectMgmt** i certyfikat **PMP**.
