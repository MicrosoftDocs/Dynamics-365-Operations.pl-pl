---
title: Dotacje dotyczące projektu
description: W tym temacie wyjaśniono, jak utworzyć lub zmodyfikować dotację.
author: RadhikaRS
manager: AnnBe
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: f4f7d347dab9f02fc474656e2f4cfba8e374480d
ms.sourcegitcommit: dfef2faf881b2db1bd0f016df36e2b838105312b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/22/2020
ms.locfileid: "3282844"
---
# <a name="project-grants"></a>Dotacje dotyczące projektu

[!include [banner](../includes/banner.md)]

Dotacja jest to suma pieniędzy podarowana na określony cel lub projekt. Zazwyczaj istnieją ograniczenia dotyczące sposobu wydania dotacji. Moduł Zarządzanie projektami i ich księgowanie umożliwia wprowadzanie i śledzenie dotacji, a także definiowanie ich relacji z projektami i umowami dotyczącymi projektów. Na przykład można wykonać następujące zadania:

- Skojarz dotacje z projektami i źródłami finansowania za pośrednictwem łączy do stron **Projekt** i **Szczegóły umowy na projekt**.
- Zmiany dotacji można wprowadzać i śledzić w miarę przechodzenia z jednego stanu do innego.
- Można śledzić i wprowadzać koszty, kwoty wnioskowane i kwoty przyznane.
- Istnieje możliwość tworzenia głównych dotacji i kojarzenia ich z poddotacjami.

Można utworzyć dotację, wprowadzając wszystkie szczegóły w nowym rekordzie lub kopiując szczegóły z istniejącej dotacji i następnie aktualizowanie ich.

## <a name="create-a-new-grant"></a>Tworzenie nowej dotacji

1. Przejdź do **Zarządzanie projektami i ich księgowanie** \> **Dotacje** \> **Dotacje**.
2. Wybierz pozycję **Nowy** \> **Dotacja**.
3. Na stronie szczegółów dotacji na skróconej karcie **Ogólne** w polu **Identyfikator dotacji** wprowadź identyfikator alfanumeryczny dotacji.
4. W polu **Nazwa dotacji** wprowadź nazwę dotacji.
5. W polu **Opis** wprowadź szczegółowe informacje o nowej dotacji.

    Większość innych pól na stronie to pola opcjonalne — ilość wprowadzonych danych zależy od użytkownika.

    Poniższa lista zawiera informacje określone na każdej skróconej karcie stronie szczegółów dotacji:

    - **Ogólne** – Wprowadzanie nazwy, stanu, opisu, celu i kwoty dotacji.
    - **Informacje kontaktowe** – Służy do wprowadzania informacji o członkach personelu i dziale zarządzającym dotacją, odbiorcy dotacji lub organizacji, która jest źródłem dotacji. Można także wskazać, czy dana organizacja jest pośrednikiem, który otrzymuje dotację, a następnie przekazuje ją dalej do innego adresata. Kliknij **Dodaj**, aby dodać informacje o kontakcie, takie jak numery telefonów oraz adresy e-mail organizacji, która przekazuje dotację.
    - **Daty i terminy** – Wprowadź daty, które są powiązane z dotacją i wnioskiem o dotację. Przykładem mogą być Data wykonania zgłoszenia, Data przesłania oraz Data zatwierdzenia lub odrzucenia dotacji.
    - **Skojarzone projekty i kontrakty projektów** — Można wprowadzać informacje na skróconej karcie tylko w przypadku, gdy pole **Stan dotacji** na skróconej karcie **Ogólne** jest ustawione jako **Aktywne** lub **Przyznane**. Wybierz spośród poniższych opcji, aby wykonać powiązane zadanie:

        - **Dodaj źródło finansowania** — dodawanie nowego źródła finansowania dotacji. Można wprowadzić wszystkie szczegóły teraz lub użyć domyślnych informacji i aktualizować je później.
        - **Dodaj umowę dotyczącą projektu** — Dodaj lub zaktualizuj informacje o umowie dotyczącej projektu.
        - **Dodaj projekt** — umożliwia dodanie lub zaktualizowanie szczegółów projektu.

    - **Konfiguracja** — umożliwia wprowadzenie szczegółowych informacji dotyczących współfinansowania, jeśli te informacje są wymagane. Wiele organizacji przyznających dotacje wymaga, aby adresaci wydali pewną określoną ilość własnych zasobów lub pieniędzy w kocie dopasowanej do kwoty dotacji. W polu **Lokalny projekt lub identyfikator śledzenia** można wprowadzić identyfikator, który różni się od identyfikatora projektu.

        > [!NOTE]
        > Jeśli część dotacji zostanie przyznana innej organizacji, ustaw opcję **Organizacja otrzymująca część dotacji** na **Tak**. W przypadku dotacji, które są przyznawane w Stanach Zjednoczonych można określić, czy dotacja zostanie przyznana na podstawie pozwolenia stanowego czy federalnego.

    - **Szczegóły wypłacania środków** – Dodawanie lub aktualizacja informacji o tym, jak często środki dotacji mogą być wycofywane, rozliczane lub wydawane.

## <a name="create-a-new-grant-from-a-copy"></a>Utwórz nową dotację z kopii

1. Przejdź do **Zarządzanie projektami i ich księgowanie** \> **Dotacje** \> **Dotacje**.
2. Wybierz **Nowe** \> **Kopia z dotacji**.
3. Wprowadź alfanumeryczny identyfikator i nazwę nowej dotacji, a następnie wybierz **OK**.
4. Na stronie szczegóły dotacji przejrzyj szczegóły skopiowanej dotacji i wprowadź wymagane zmiany. Większość pól na stronie jest opcjonalna.

## <a name="view-or-modify-grant-details"></a>Wyświetl lub zmodyfikuj szczegóły dotacji

1. Przejdź do **Zarządzanie projektami i ich księgowanie** \> **Dotacje** \> **Dotacje**.
2. Wybierz dotację do zmodyfikowania.
3. W okienku akcji na karcie **Dotacja** w grupie **Obsługa** wybierz opcję **Edytuj**.
4. Przejrzyj szczegóły dotyczące dotacji i wprowadź wymagane zmiany.
