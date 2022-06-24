---
title: Konfigurowanie parametrów dla automatyzacji procesów windykacji
description: W tym artykule opisano parametry wpływające na procesy zautomatyzowanej windykacji i przedstawiono wskazówki dotyczące ich konfigurowania w taki sposób, aby proces automatyczny odzwierciedlał zamiary i oczekiwania użytkownika.
author: JodiChristiansen
ms.date: 08/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-26
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: c5d0f801c47ef2d98d8ba410dc593bd7640839c1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900050"
---
# <a name="configure-parameters-for-collection-process-automation"></a>Konfigurowanie parametrów dla automatyzacji procesów windykacji

[!include [banner](../includes/banner.md)]

W tym artykule opisano parametry wpływające na procesy zautomatyzowanej windykacji i przedstawiono wskazówki dotyczące ich konfigurowania w taki sposób, aby proces automatyczny odzwierciedlał zamiary i oczekiwania użytkownika. Aby uzyskać informacje dotyczące automatyzowania procesów windykacji, zobacz temat [Automatyzacja procesów windykacji](collections-process-automate.md).

## <a name="general"></a>Ogólny
Służy do wprowadzania liczby w **Procencie odbiorców na zadanie wsadowe** w celu określenia liczby zadań wsadowych na proces automatyzacji. Ustaw opcję **Automatyczne wysyłanie ponagleń** na **Tak**, dzięki czemu typ akcji ponaglenia spowoduje wysłanie ponaglenia podczas automatyzacji. Ustaw opcję **Utwórz działania dla automatyzacji** na wartość **Tak**, aby utworzyć i zamknąć działania dla typów akcji bez działań, aby wyświetlić wszystkie kroki wykonane automatycznie dla konta. Zdefiniuj liczbę dni przechowywania historii windykacji w części **Dni przechowywania historii automatyzacji procesów windykacji**. Gdy faktura osiągnie ostatni krok procesu windykacji, nie będzie ona używana do tworzenia przyszłych typów akcji automatyzacji procesów, jeśli ustawienie **Wyklucz fakturę po aktywacji ostatniego kroku procesu** ma wartość **Tak**. Następna najstarsza faktura określa następny krok automatyzacji procesu, aby zapewnić kontynuację akcji automatyzacji procesów windykacji. 

## <a name="payment-predictions"></a>Przewidywania płatności
Począwszy od wersji 10.0.21 prognozy płatności odbiorcy znalezione w rozwiązaniu Finance Insights wskazują, czy faktura zostanie zapłacona w terminie, późno czy bardzo późno. W aplikacji Finance Insights można skonfigurować każdą z tych kategorii. Jeśli przewiduje się, że faktura będzie zapłacona późno, ważne jest rozpocząć proces windykacji przed terminem płatności faktury. Te prognozy mogą służyć do tworzenia działań windykacji po uruchomieniu automatyzacji procesów windykacji. Ustaw opcję **Włącz przewidywanie płatności** wartość **Tak**, by używać prognoz płatności odbiorcy do tworzenia prognoz płatności działań windykacji na podstawie prawdopodobieństwa, że faktura zostanie zapłacona z opóźnieniem. 

Aby uzyskać więcej informacji o przewidywaniach płatności odbiorcy i Finance Insights, zobacz [Przewidywania płatności odbiorcy](payment-insights-overview.md).

Podczas uruchomienia modelu prognoz płatności odbiorcy przypisuje on wartość procentową do prognozy dotyczącej faktury opłacanej na czas, późno lub bardzo późno. Tych informacji można używać do automatycznego rozpoczynania działań windykacji za pomocą automatyzacji procesów windykacji w przypadkach, gdy oczekiwana płatność jest opóźniona. Te wartości procentowe można wyświetlić w **Prognozach płatności według odbiorcy** lub **Prognozach płatności według transakcji** w obszarze **Kredyty i windykacja > Windykacja**. 

Jeśli prognoza średniej płatności dla faktury dla odbiorcy jest mniejsza niż procent testu porównawczego, nie jest tworzone żadne działanie. Jeśli prognoza faktury jest większa lub równa procentowi testu porównawczego, tworzone jest jedno działanie na odbiorcę. W opcji **Prognoza: opóźnienie** wprowadź **Wartość procentowa testu porównawczego**, od kiedy automatyzacja procesów windykacji ma tworzyć działania windykacji. Jest to wartość agregacji płatności później i bardzo późnej. Wybierz **Szablon dokumentu biznesowego** do użycia dla utworzonego działania lub utwórz nowy. Identyfikuje on **Typ**, **Cel** i **Dni do zamknięcia działania**. Wprowadź **Uwagi**, które będą domyślnym opisem podczas tworzenia działania. W opcji **Prognoza: duże opóźnienie** wprowadź **Wartość procentowa testu porównawczego**, od kiedy automatyzacja procesów windykacji ma tworzyć działania windykacji dla odbiorcy, dla którego przewidziano bardzo późne opłacenie faktury. Wybierz **Szablon dokumentu biznesowego** do użycia dla tworzonego działania. Identyfikuje on **Typ**, **Cel** i **Dni do zamknięcia działania**. Wprowadź **Uwagi**, które będą domyślnym opisem podczas tworzenia działania. 

### <a name="example"></a>Przykład
Jeśli procent opóźnienia testu porównawczego jest ustawiony na 60%. Gdy prognozy płatności odbiorcy są uruchomione dla każdej faktury, system przypisuje wartość procentową prognozy zapłaty na czas, późno lub bardzo późno. Jeśli prognoza płatności, że faktura zostanie zapłacona później, wynosi 59% lub mniej, w automatycznym procesie windykacji nie zostanie utworzone żadne działanie dotyczące windykacji dla faktury. Jeśli prognoza płatności odbiorcy dla faktury jest większa lub równa 60%, podczas automatyzacji procesów windykacji jest tworzone działanie dotyczące windykacji. 

> [!NOTE]
> Prognoza dużego opóźnienia jest oceniana przed prognozą opóźnienia, ponieważ bardzo późno zawiera faktury, które są przewidywane do zapłaty późno. Proces windykacji generuje tylko jedno działanie, jeśli faktura uwzględnia testy porównawcze „późno” i „bardzo późno”. W takim przypadku system używa bardzo późnej czynności i dokumentu biznesowego, ponieważ bardzo późno ma o wiele wyższy priorytet. Inne akcje, które zostały już wygenerowane, nie zostaną wygenerowane po raz drugi.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
