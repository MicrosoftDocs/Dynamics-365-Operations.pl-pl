---
title: "Przykładowe czeki od dostawców w raportowaniu elektronicznym"
description: "Ten temat zawiera ogólne informacje o używaniu przykładowych formatów czeków w module Raportowanie elektroniczne."
author: twheeloc
manager: AnnBe
ms.date: 06/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.assetid: 
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 6702ac241c41cc99d96bc46a515837235b3ae651
ms.contentlocale: pl-pl
ms.lasthandoff: 03/26/2018

---

[!include[banner](../includes/banner.md)]

# <a name="electronic-reporting-sample-check-formats"></a>Przykładowe formaty czeków w raportowaniu elektronicznym

Modułu Raportowanie elektroniczne (ER) można używać do formatowania czeków od dostawców. Na rynku jest dostępnych wiele formatów czeków specyficznych dla banków i wystawców czeków. Przykładowe formaty czeków zostały umieszczone w modelu płacenia czekami w repozytorium narzędzie ER. Te przykładowe czeki są zatytułowane **Czek w środku (Stany Zjednoczone)** i **Czek na górze, pokwitowanie pod spodem (Stany Zjednoczone)**.

## <a name="what-check-formats-are-currently-supported"></a>Które formaty czeków są obecnie obsługiwane?

Należy zawsze przejść do biblioteki zasobów wspólnych w usłudze Microsoft Dynamics Lifecycle Services (LCS) i wyświetlić aktualną listę dostępnych plików, które mają typ składnika aktywów **Konfiguracja GER**. Następna sekcja — „Co trzeba skonfigurować?” — zawiera łącze do tematu, który wyjaśnia sposób tworzenia repozytorium usługi LCS na potrzeby przeglądania dostępnych konfiguracji i importowania wybranych konfiguracji.

Program Microsoft Dynamics 365 for Finance and Operations zawiera przykładowy format, w którym czek jest na górze, a pod spodem znajdują się dwie sekcje przekazu. Jest również przykładowy formularz, w którym czek znajduje się na środku, między dwoma sekcjami przekazu. Te przykładowe formaty odpowiadają formatowi czeków firmowych Deluxe.

## <a name="what-do-i-have-to-set-up"></a>Co trzeba skonfigurować?

- Aby możliwe było drukowanie czeków przy użyciu modułu ER, co najmniej jedna aktywna konfiguracja czeku musi zostać zaimportowana do konfiguracji ER. Instrukcje znajdują się w temacie [Pobieranie konfiguracji modułu Raportowanie elektroniczne z usługi Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).
- Podczas konfigurowania czeków w module Zarządzanie gotówką i bankami dla rachunku bankowego zaznacz pole wyboru **Ogólny elektroniczny format eksportu**, a następnie wybierz odpowiedni format czeku jako konfigurację formatu eksportu.
- Ponadto należy określić liczbę wierszy pokwitowania, które zostaną wydrukowane na przekazie. Pamiętaj, aby przy obliczaniu tej liczby uwzględnić wiersze nagłówka. W dwóch przykładowych formatach czeku zaleca się, aby było 17 wierszy pokwitowania. Jednak ta liczba będzie się różnić w zależności od wzorów blankietów czeków i sterowników drukarki.
- Zalecamy wydrukowanie testowego czeku w celu sprawdzania poprawności jego układu. Aby wydrukować czek testowy, zaznacz opcję **Drukowanie testu**. Przykładowe formaty czeków działają najlepiej, gdy w zaawansowanych właściwościach drukarki dla programu Microsoft Excel w opcji **Marginesy** jest ustawiona wartość **Brak**. Po wygenerowaniu testowego czeku włącz edytowanie danych wyjściowych programu Excel i skonfiguruj układ strony tak, aby wszystkie marginesy miały ustawioną wartość **0** (zero). Porównaj kopię testową czeku z używanymi blankietami czeków i koryguj ustawienia, aż osiągniesz zadowalające wyrównanie.
- Podczas generowania płatności dla skonfigurowanego konta bankowego w arkuszu płatności czeki zostaną wydrukowanie zgodnie z podanym formatem.

Aby uzyskać więcej informacji, zobacz [Modyfikowanie formatu raportowania elektronicznego](../../dev-itpro/analytics/modify-electronic-reporting-format-reapply-excel-template.md).

