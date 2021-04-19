---
title: Ustanawianie wspólnych wartości dla zarządzania zmianami inżynieryjnymi
description: W tym temacie opisano sposób ustalania typowych wartości używanych dla parametrów w różnych częściach zarządzania zmianami inżynieryjnymi.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgProductParameters, EngChgEcmSeverityTable, EngChgEcmSeverityRuleSet, EngChgEcmSeverityLookup,EngChgEcmSeverityChart,EngChgEcmRequestSeverityChart,EngChgEcmPriorityTable, EngChgEcmPriorityLookup, EngChgEcmPriorityChart, EngChgEcmMaterialDisposition, EngChgEcmEH
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: fadfb44b0d332e0c21d1c2bc3f2c2983d0bb8d1d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830059"
---
# <a name="establish-common-values-for-engineering-change-management"></a>Ustanawianie wspólnych wartości dla zarządzania zmianami inżynieryjnymi

[!include [banner](../includes/banner.md)]

Podczas konfigurowania zarządzania zmianami technologicznymi należy utworzyć kilka zbiorów wartości, które będą używane do wypełniania list rozwijanych w innych częściach interfejsu użytkownika (UI). Te wartości należy określić w zależności od typów wytwarzanych produktów i określonych potrzeb biznesowych.

## <a name="engineering-change-categories"></a>Kategorie zmian projektowych

Kategorie zmiany technologiczne umożliwiają organizowanie zleceń zmiany inżyniera, dzięki czemu można je łatwiej zarządzać i recenzować. Na przykład może okazać się przydatne skonfigurowanie przepływu pracy, gdzie w zależności od kategorii określony dział musi przejrzeć proponowane zmiany. Z tego względu w ramach tego zlecenia zmiany technologiczne zawierają pole **Kategoria**.

Aby ustalić zbiór kategorii zmian inżynieryjnych używanych w firmie, przejdź do **Zarządzanie zmianami inżynierskimi\> Konfiguracja \>Zarządzanie zmianami inżynierskimi \>Kategorie zmian inżynierskich**. Za pomocą przycisków w okienku akcji można dodawać, usuwać i edytować wartości oraz rozmieszczać je w kolejności, w jakiej powinny być wyświetlane na listach rozwijanych, gdzie są wyświetlane.

## <a name="engineering-change-priorities"></a>Priorytety zmian projektowych

Aby wskazać stopień ważności lub pilności zlecenia zmiany technologiczne, należy skorzystać z priorytetów zmian technologicznych. Mogą one pomóc śledzić znaczenie zlecenia zmiany inżyniera, dzięki czemu można łatwo określić, które zamówienia powinny być przetwarzane jako pierwsze i jak szybko.

Aby ustalić zbiór priorytetów zmian inżynieryjnych używanych w firmie, przejdź do **Zarządzanie zmianami inżynierskimi\> Konfiguracja \>Zarządzanie zmianami inżynierskimi \>Priorytety zmian inżynierskich**. Za pomocą przycisków w okienku akcji można dodawać, usuwać i edytować wartości oraz rozmieszczać je w kolejności, w jakiej powinny być wyświetlane na listach rozwijanych, gdzie są wyświetlane.

## <a name="engineering-change-reasons"></a>Przyczyna zmiany projektowej

Techniczne przyczyny zmiany wskazują na przyczynę lub charakter zmiany w zamówieniu zmiany.

Aby ustalić zbiór powodów zmian inżynieryjnych używanych w firmie, przejdź do **Zarządzanie zmianami inżynierskimi\> Konfiguracja \>Zarządzanie zmianami inżynierskimi \>Powody zmian inżynierskich**. Za pomocą przycisków w okienku akcji można dodawać, usuwać i edytować wartości oraz rozmieszczać je w kolejności, w jakiej powinny być wyświetlane na listach rozwijanych, gdzie są wyświetlane.

## <a name="material-disposal-codes"></a>Kody likwidacji materiału

Kody likwidacji materiałów służą do kategoryzowania materiałów używanych w wyrobach gotowych lub składników, które muszą zostać zlikwidowane w określony sposób, lub wymagają pewnej obróbki, aby mogły zostać dodane do zwykłego kosza. Po dodaniu odpowiedniego produktu do zlecenia zmiany technologiczne można przypisać mu kod likwidacji jako część szczegółów dotyczących zmiany.

Aby ustalić zbiór kodów usuwania materiałów używanych w firmie, przejdź do **Zarządzanie zmianami inżynierskimi\> Konfiguracja \>Zarządzanie zmianami inżynierskimi \>Kody usuwania materiałów**. Za pomocą przycisków w okienku akcji można dodawać, usuwać i edytować wartości oraz rozmieszczać je w kolejności, w jakiej powinny być wyświetlane na listach rozwijanych, gdzie są wyświetlane.

## <a name="received-customer-approval"></a>Uzyskane zatwierdzenie odbiorcy

Podczas projektowania produktów dla określonego odbiorcy często należy sprawdzić poprawność projektu i specyfikacji, aby można było skonfigurować produkt jako gotowy. **Pole zatwierdzenie odebrane odbiorcy** umożliwia wskazanie, jak daleko w procesie zatwierdzania odbiorców produkt jest i/lub czy zatwierdzenie zostało odebrane.

Aby ustalić zbiór otrzymanych wartości zatwierdzeń przez klienta używanych w firmie, przejdź do **Zarządzanie zmianami inżynierskimi\> Konfiguracja \>Zarządzanie zmianami inżynierskimi \>Otrzymane zatwierdzenia od klienta**. Za pomocą przycisków w okienku akcji można dodawać, usuwać i edytować wartości oraz rozmieszczać je w kolejności, w jakiej powinny być wyświetlane na listach rozwijanych, gdzie są wyświetlane.

## <a name="engineering-change--environmental-health-and-safety-codes"></a>Zmiana inżynieryjna — kody BHPiOŚ

Jeśli w wytwarzaniu produktu należy wziąć pod uwagę standardowe przepisy dotyczące ochrony zdrowia i bezpieczeństwa w środowisku naturalnym, lub odpowiednie przepisy lub procedury właściwe dla danego przedsiębiorstwa, można je zdefiniować za pomocą kodów BHPiOŚ. W zamówieniu zmiany inżynieryjnej można wskazać, które kody mają być stosowane do produkcji produktu podczas edytowania szczegółów produktu, którego dotyczy problem.

Aby ustalić zbiór wartości BHPiOŚ używanych w firmie, przejdź do **Zarządzanie zmianami inżynierskimi\> Konfiguracja \>Zarządzanie zmianami inżynierskimi \>Kody BHPiOŚ**. Za pomocą przycisków w okienku akcji można dodawać, usuwać i edytować wartości oraz rozmieszczać je w kolejności, w jakiej powinny być wyświetlane na listach rozwijanych, gdzie są wyświetlane.

## <a name="engineering-change-severities"></a>Poziomy ważności zmian projektowych

W celu określenia poziomu wpływu, jaki ma zastosowanie do produktów w zleceniu na zmiany inżynieryjne, należy zastosować wagę zmian inżynieryjnych.

Aby ustalić zbiór wag zmian inżynieryjnych używanych w firmie, przejdź do **Zarządzanie zmianami inżynierskimi\> Konfiguracja \>Zarządzanie zmianami inżynierskimi \>Wagi zmian inżynierskich**. Za pomocą przycisków w okienku akcji można dodawać, usuwać i edytować wartości oraz rozmieszczać je w kolejności, w jakiej powinny być wyświetlane na listach rozwijanych, gdzie są wyświetlane.

Można ustanowić reguły dotyczące każdego tworzonego poziomu ważności. Aby uzyskać więcej informacji o przypisywaniu tych reguł, zapoznaj się z następną sekcją.

## <a name="engineering-change-severity-rule-sets"></a>Zestawy reguł ważności zmian projektowych

Zestawy reguł ważności zmiany technologiczne służą do ustanawiania grupy reguł, których można wykorzystywać do automatycznego obliczania ważności zlecenia zmiany na podstawie typu zmian w produktach, których dotyczy problem. Aby zastosować reguły ważności, otwórz stronę **Parametry zarządzania zmianami inżynieryjnymi** i w polu **Reguła ważności** określ wartość, która będzie *Obliczana* lub *Obliczana automatycznie*.

Gdy system ocenia wagę, przetwarza reguły w kolejności, w jakiej są wyświetlane na stronie, od góry do dołu. Aby reguła została wybrana i mieć ustalony priorytet, muszą być spełnione wszystkie reguły w zestawie reguł.

Aby skonfigurować reguły dotyczące wszystkich zdefiniowanych poziomów ważności zmian, przejdź do **Zarządzanie zmianami inżynieryjnymi\> Konfiguracja \>Zarządzanie zmianami inżynieryjnymi\> Zestawy reguł dotyczące zmiany ważności zmian inżynieryjnych**. Następnie wykonaj jeden z następujących kroków.

- Aby utworzyć nowy zestaw zasad, wybierz opcję **Nowa** w okienku akcji, a następnie określ te pola zgodnie z poniższymi podsekcjami.
- Aby edytować istniejący zestaw zasad, wybierz je w okienku listy, wybierz opcję **Edytuj** w okienku akcji, a następnie określ pola w sposób opisany w poniższych podsekcjach.
- Aby usunąć istniejący zestaw zasad, zaznacz je w okienku listy, a następnie wybierz **Usuń** w okienku akcji.
- Aby zmienić kolejność listy zestawów reguł, wybierz zestaw reguł w okienku listy, a następnie użyj przycisków **w górę** i **w dół** w okienku akcji, aby zmienić ich położenie.

Dla każdego zestawu reguł ustaw następujące pola:

- **Ważność** — umożliwia wybór poziomu ważności, dla którego mają być ustanawiane reguły. Do tworzenia i nadawanie nazw poziomom służy strona **Ważności zmian inżynieryjnych**. (Więcej informacji można znaleźć w poprzedniej sekcji.)

Użyj przycisków na skróconej karcie **Reguły**, aby dodać lub usunąć regułę dotyczącą bieżącego ustawienia ważności. Każda reguła ma pole **Reguły** i **Nazwa**. Reguły są ustanawiane przez system i wskazują typy zmian, jakie może mieć produkt. Nazwa określa typ zmiany.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]