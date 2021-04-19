---
title: Ustawienia podróży wieloetapowej
description: W tym temacie opisano, jak skonfigurować podróże wieloetapowe dla modułu kosztów z wyładunkiem.
author: sherry-zheng
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMLegTable, ITMJourneyTable, ITMActivityTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: e1377b7453622e5bed711753fc2d99258d3c5951
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833768"
---
# <a name="multi-leg-journey-setup"></a>Ustawienia podróży wieloetapowej

[!include [banner](../../includes/banner.md)]

W tym temacie opisano, jak skonfigurować podróże wieloetapowe dla modułu **kosztów z wyładunkiem**.

## <a name="legs"></a>Etapy

Stopy są używane do identyfikowania oddzielnych części podróży. Każda noga jest zbudowane przez wybranie portów wysyłki „do” i „z” oraz metody transportu stosowanej dla tego etapu. Czasy realizacji można skojarzyć z każdym etapem. Czasy realizacji ułatwiają śledzenie wysyłki, a także mogą być używane do obliczania szacowanej daty dostawy towarów w podróży. Ponadto po ukończeniu podróży stan podróży, kontener wysyłkowy i skojarzone wiersze zamówienia zakupu mogą zostać zaktualizowane za pomocą konfiguracji kontroli śledzenia. Podróży można używać w ramach jednego szablonu lub używać ich ponownie w wielu szablonach podróży. Załadunek kontenerów, odprawy celne i transport lokalny są zwykle ustawione jako nogi, a dla nich używany jest niespecyficzny port wysyłkowy.

Aby pracować z etapami, przejdź do **Koszt z wyładunkiem \> Ustawienia podróży wieloetapowej \> Etapy**. Można tam wyświetlać, otwierać, tworzyć i usuwać etapy. W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.

| Pole | opis |
|---|---|
| Etap | Wprowadź unikalną nazwę/numer identyfikacyjny etapu podróży. |
| opis | Umożliwia wprowadzenie krótkiego opisu etapu podróży. Zazwyczaj ten opis określa port „do” i „od” lub część podróży. |
| Port źródłowy | Wprowadź punkt pochodzenia towarów w etapie. |
| Port docelowy | Wprowadź miejsce przeznaczenia towaru w etapie. |
| Metoda dostawy | Wprowadź metodę transportu dla etapu. |

## <a name="journey-templates"></a>Szablony podróży

Szablon podróży definiuje podróż wieloetapową między dwoma portami, w której towary przewożone są podczas podróży. Odcinki podróży są łączone w celu określenia czasu, jaki będzie potrzebny na transport towarów z miejsca pochodzenia sprzedawcy do końcowego miejsca przeznaczenia w magazynie. Gdy odcinki zostaną umieszczone na szablonie podróży w określonej kolejności, czasy realizacji określą datę każdego etapu i status podróży, kontener i linie zakupu dla podróży. [Centrum kontroli śledzenia](delivery-information-setup.md) służy do konfigurowania czasów realizacji powiązanych z każdym etapem tworzącym szablon podróży. Szablon wyjazdu jest również używany przy ustawianiu kosztów automatycznych podróży. Po zdefiniowaniu podróży koszt związany z transportem towarów można zdefiniować na stronie kosztów auto.

Aby pracować z szablonami podróży, przejdź do **Koszt z wyładunkiem \> Ustawienia podróży wieloetapowej \> Szablony podróży**. Można tam wyświetlać, otwierać, tworzyć i usuwać szablony podróży.

Dla każdego szablonu wyjazdu należy ustawić następujące pola w nagłówku.

| Pole | opis |
|---|---|
| Szablon podróży | Wprowadź unikalną nazwę/numer identyfikacyjny szablonu podróży. Szablon podróży zazwyczaj opisuje punkt początkowy i punkt docelowy podróży. |
| opis | Umożliwia wprowadzenie krótkiego opisu szablonu podróży. Opis zazwyczaj wskazuje porty „do” i „od” oraz typ podróży. |

W sekcji **Wiersze** dodaj wiersz dla każdej części wyjazdu i umieść wiersze w kolejności. Aby zmienić kolejność wierszy, użyj strzałek **W górę** i **W dół** na pasku narzędzi. W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego wiersza.

| Pole | opis |
|---|---|
| Etap | Wybierz etap do dodania do podróży. |
| opis | Opis etapu. |
| Port źródłowy | Port będący punktem pochodzenia towaru w etapie. Ten port jest portem „do” używanym do określania kosztów automatycznych dla podróży. |
| Port docelowy | Ostateczny port docelowy towarów w etapie. |
| Metoda dostawy | Sposób dostawy stosowany w przypadku etapu. |
| Port źródłowy podróży | Jeśli port określony dla etapu jest używany do określania kosztów automatycznych, zaznacz to pole wyboru, aby zidentyfikować go jako „podróż z” portu. Ten port będzie wyświetlany w nagłówku podróży. |
| Port docelowy podróży | Jeśli port określony dla etapu jest używany do określania kosztów automatycznych, zaznacz to pole wyboru, aby zidentyfikować go jako „podróż do” portu. Ten port będzie wyświetlany w nagłówku podróży. |
| Firma przewozowa | Wybierz firmę przewozową używaną dla etapu. |

## <a name="activities"></a>Działania

Ustawienia na stronie **Działania** ustalają typy działań, które mogą występować na docelowym porcie etapu. Użytkownicy, którzy pracują na stronie **Wszystkie kontenery wysyłkowe**, mogą wybierać spośród tych wartości, kiedy szacują czas trwania każdego działania i rejestrują rzeczywisty czas trwania dla celów porównania.

Aby skonfigurować działania, przejdź do **Koszt z wyładunkiem \> Ustawienia podróży wieloetapowej \> Działania**. Można tam dodawać, usuwać i edytować działania za pomocą przycisków w okienku akcji.

W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego działania w siatce.

| Pole | opis |
|---|---|
| Działanie | Nazwa działania. |
| opis | Opis działania. |
| Firma przewozowa | Konto dostawcy firmy przewozowej, która jest powiązana z działaniem. |
