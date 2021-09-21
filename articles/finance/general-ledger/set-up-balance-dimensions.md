---
title: Jak ustawić wymiary finansowe bilansowania?
description: W tym temacie opisano opcje konfigurowania i używania funkcji wymiaru finansowego bilansowania.
author: kweekley
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionDetails
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-08-17
ms.dyn365.ops.version: 10.0.210
ms.openlocfilehash: 188c15c4cb0c295a9fcbb08273ddb391fbc29e24
ms.sourcegitcommit: b4c78655f2ab4b0e7ead96dfb9cf087a18014253
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2021
ms.locfileid: "7468947"
---
# <a name="how-do-i-set-up-balancing-financial-dimensions"></a>Jak ustawić wymiary finansowe bilansowania?

[!include [banner](../includes/banner.md)]

W tym temacie opisano opcje konfigurowania i używania funkcji wymiaru finansowego bilansowania.

## <a name="symptom"></a>Objaw

Istnieją dwie opcje konfigurowania wymiarów finansowych bilansowania. Pierwszą opcją jest użycie pola **Wymiar finansowy bilansowania** na stronie konfiguracji **Księga** (**Księga główna \> Konfiguracja księgi głównej \> Księga**). Drugą opcją jest użycie **Wymagaj, aby wymiar był zbilansowany** na stronie **Wymiary finansowe** (**Księga główna > Plan kont \> Wymiary \> Wymiary finansowe**). W tym temacie wyjaśniono różnicę między tymi dwiema opcjami.

## <a name="resolution"></a>Rozwiązanie

Organizacje zwykle używają wymiarów bilansowania do generowania bilansu, który jest zbilansowany na poziomie wymiaru finansowego. Włączenie każdej z tych funkcji nie spowoduje zbilansowania zaksięgowanych wymiarów niezbilansowanych. Przed włączeniem jednej z funkcji należy ręcznie skorygować wpisy, aby zbilansować bilans.

Te dwie opcje wykluczają się wzajemnie. Wybór jednej z opcji przez organizację powinien zależeć od jej wymagań biznesowych. Często słyszymy o klientach, którzy definiują wymiar bilansowania w konfiguracji księgi i konfiguracji wymiarów finansowych, a następnie wykonują dodatkowe ustawienia, które są wymagane. Nadal jednak nie mogą księgować z powodu niezbilansowania na poziomie wymiaru finansowego.

W poniższych sekcjach opisano dwie opcje oraz sposób ich konfiguracji.

### <a name="ledger--balancing-financial-dimension"></a>Księga — bilansowanie wymiaru finansowego

Wymiar bilansowania na stronie konfiguracji **Księga** służy do włączania księgowania międzyjednostkowego. Aby włączyć tę funkcję, należy wykonać następujące kroki.

1. Określ, który wymiar finansowy będzie wymiarem bilansowania.

    - Ta funkcja umożliwia wybranie tylko jednego wymiaru finansowego jako wymiaru bilansowania.
    - Jeszcze nie wybieraj wymiaru na stronie konfiguracji **Księga**.
    - Upewnij się, że bilans jest już zbilansowany dla wybranego wymiaru finansowego.

2. Zaktualizuj strukturę konta wymiaru finansowego bilansowania.

    - Wymiar finansowy bilansowania musi być uwzględniony we wszystkich strukturach kont przypisanych do księgi.
    - Wymiar finansowy nie może zezwalać na wartości puste w strukturze konta. To ograniczenie gwarantuje, że każdy zapis księgowy, który jest księgowany w księdze głównej, zawiera wartość wymiaru finansowego. Pusty wymiar nie jest prawidłowy, gdy są używane wymiary bilansowania.

3. Na stronie **Konta transakcji automatycznych** (**Księga główna \> Ustawienia księgowania \> Konta dla transakcji automatycznych**) zdefiniuj konta główne międzyjednostkowych kont debetowych i kredytowych.
4. W polu **Wymiar finansowy bilansowania** na stronie konfiguracji **Księga** (**Księga główna \> Konfiguracja księgi głównej \> Księga**)wybierz wymiar finansowy, który będzie używany do bilansowania.

Jeśli wybrany wymiar finansowy nie jest zbilansowany podczas wprowadzania i księgowania transakcji, system automatycznie doda wpisy debetowe lub kredytowe wymagane do zbilansowania wpisu księgowania podczas księgowania. Debetowe i kredytowe konta księgi dla transakcji międzyjednostkowej są wyświetlane w zaksięgowanym załączniku w księdze głównej. Nie będą jednak wyświetlane w arkuszach ani dokumentach źródłowych, dla których zaksięgowano zapisy księgowe.

### <a name="financial-dimensions--require-the-dimension-to-be-balanced"></a>Wymiary finansowe — Wymagaj, aby wymiar był zbilansowany

Chociaż wymiar bilansowania na stronie **Wymiary finansowe** jest zwykle używany przez firmy z sektora publicznego, ta funkcja nie jest połączona z żadnym kluczem konfiguracji sektora publicznego. Ze względu na brak ograniczeń w systemie można używać tej funkcji, nawet jeśli organizacja nie jest podmiotem z sektora publicznego.

Ta funkcja jest zazwyczaj używana przez klientów z sektora publicznego, ponieważ wymaga, aby definicje księgowania były używane do automatycznego bilansowania każdej transakcji. Nie używa ona międzyjednostkowych kont debetowych i kredytowych zdefiniowanych na stronie **Konta transakcji automatycznych** do automatycznego bilansowania wpisów księgowych. Jeśli po zastosowaniu definicji księgowania zapis księgowy nie jest zbilansowany na poziomie wymiaru, transakcja nie zostanie zaksięgowana, nawet jeśli są zdefiniowane międzyjednostkowe konta debetowe i kredytowe.

Często słyszymy o klientach, którzy definiują ten wymiar bilansowania w ustawieniach księgi i ustawieniach wymiarów finansowych. W takim przypadku system używa funkcji wymiarów finansowych. Ustawienia wymiarów bilansowania na poziomie wymiaru finansowego mają pierwszeństwo podczas księgowania. Księgowanie nie powiedzie się, jeśli definicja księgowania nie utworzy wpisu księgowania bilansowego na poziomie wymiaru finansowego.

Aby włączyć używanie wymiaru bilansowania na poziomie wymiaru finansowego, należy wykonać następujące kroki.

1. Określ, które wymiary finansowe będą wymiarami bilansowania.

    - Jako wymiar bilansowania można ustawić więcej niż jeden wymiar finansowy.
    - Jeszcze nie ustawiaj wymiarów finansowych, które będą wymagane do zbilansowania transakcji, na stronie **Wymiary finansowe**.

2. Zdefiniuj definicje księgowania dla każdego typu arkusza lub dokumentu źródłowego używanego przez organizację. Definicje księgowania zużywają konta księgi z niezaksięgowanych arkuszy lub dokumentów źródłowych jako kryteria dopasowania. W ten sposób w definicji księgowania zwracane są „wygenerowane wpisy”, które stają się wpisami księgowymi. Jeśli definicja księgowania jest prawidłowo ustawiona, generowany wpis zawiera konta księgowe z kryteriami dopasowania oraz konta dodatkowe służące do zbilansowania wpisu księgowania na poziomie wymiaru. Aby uzyskać więcej informacji, zobacz [Definicje księgowania](posting-definitions.md). 
   
   Definicje księgowania nie są obsługiwane w przypadku każdego typu transakcji. Na przykład nie można zdefiniować definicji księgowania dla żadnych transakcji wprowadzonych za pomocą arkusza finansowego lub arkusza środków trwałych. Jeśli nie można zdefiniować definicji księgowania dla arkusza lub dokumentu źródłowego, transakcja musi zostać ręcznie zbilansowana na poziomie wartości wymiaru finansowego. Jeśli na przykład zostanie dokonany wpis w arkuszu ogólnym, a wymiarem bilansowania jest wymiar Dział, należy upewnić się, że każda wartość działu jest zbilansowana.  Jeśli wymiar nie jest zbilansowany dla każdej wartości działu, załącznik nie będzie księgowany do czasu skorygowania niezbilansowania przez ręczne dodanie międzyjednostkowego debetu lub kredytu do załącznika. 

    > [!IMPORTANT]
    > Jeśli należy ręcznie zbilansować dużą liczbę transakcji, **nie** należy używać funkcji wymiaru bilansowania na stronie **Wymiary finansowe**. Zamiast tego należy użyć funkcji wymiaru bilansowania na stronie konfiguracji **Księga**.

3. Po zdefiniowaniu definicji księgowania wymiary finansowe można oznaczać jako wymagane do bilansowania.

Podczas wprowadzania i księgowania transakcji definicje księgowania są wywoływane w celu określenia zapisów księgowych. Jeśli wymiary finansowe są zbilansowane, sprawdzanie poprawności następuje po ustaleniu wpisów księgowych. Jeśli wymiary finansowe nie są zbilansowane, transakcja nie zostanie zaksięgowana i zostanie wyświetlony komunikat informujący, że kwoty po stronie debetowej i kredytowej nie są równe w określonym wymiarze.
