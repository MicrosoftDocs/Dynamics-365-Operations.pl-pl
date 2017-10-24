---
title: "Obszar roboczy Zarządzanie środkami trwałymi"
description: "Ten temat zawiera informacje o obszarze roboczym Zarządzanie środkami trwałymi. Ten obszar roboczy pokazuje informacje związane z środkami trwałymi wprowadzonymi w systemie. Zawiera widoki podsumowania i analizy."
author: saraschi
manager: AnnBe
ms.date: 06/06/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.assetid: 
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: c87cd29f46acb44faddaf5552de21fb8f4c5c71d
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="fixed-asset-management-workspace"></a>Obszar roboczy Zarządzanie środkami trwałymi

[!include[banner](../includes/banner.md)]

Obszar roboczy **Zarządzanie środkami trwałymi** pokazuje informacje związane z środkami trwałymi wprowadzonymi w systemie. Zawiera widoki podsumowania i analizy. Karta **Moja praca** zawiera kafelki podsumowań, szczegóły środków trwałych oraz pokrewne informacje o środkach trwałych w bieżącej firmie. Można również dodawać analizy do sekcji analiz w narzędziu Power BI bezpośrednio w obszarze roboczym. Karta **Analizy — wszystkie firmy** wykorzystuje funkcje usługi Microsoft Power BI, aby pokazać wizualizacje dotyczące środków trwałych we wszystkich firmach.

## <a name="my-work"></a>Moja praca

### <a name="summary"></a>Sumarycznie

Kafelki w sekcji **Podsumowanie** zawierają przegląd środków trwałych firmy. Informacje obejmują mierniki dotyczące składników aktywów, które jeszcze nie zostały nabyte, nabyte w bieżącym roku oraz zlikwidowane w bieżącym roku. Sekcja **Podsumowanie** umożliwia również szybkie przejście do strony listy **Środki trwałe**, propozycji amortyzacji za pomocą procesu wsadowego oraz arkusza środków trwałych.

### <a name="find-fixed-assets"></a>Znajdź środki trwałe

Sekcja **Znajdź środki trwałe** pozwala szybko wyszukiwać zasoby poprzez podanie numeru, grupy, nazwy, lokalizacji lub osoby odpowiedzialnej za środek trwały. Na liście będą wyświetlane wszystkie środki trwałe spełniające kryteria wyszukiwania.

Z listy można otwierać następujące strony:

 - Strona **Szczegóły** dla środka trwałego
 - Strona **Księgi** dla wszystkich ksiąg skojarzonych ze środkiem trwałym
 - Strona **Wyceny środków trwałych**

### <a name="valuations"></a>Wyceny

Strona **Wyceny środków trwałych** pozwala zobaczyć w jednym miejscu najważniejsze informacje o środku trwałym, a także szczegóły wszystkich skojarzonych z nim ksiąg. Opcja **Salda** w lewej górnej części strony pokazuje bieżącą wycenę dla każdej księgi skojarzonej ze środkiem trwałym. Można przechodzić wstecz od wartości, aby wyświetlić szczegółowe transakcji składające się na wartość podsumowania. Opcja **Profil** w lewej górnej części strony pokazuje harmonogram amortyzacji dla każdej księgi skojarzonej ze środkiem trwałym.

Dostęp do strony **Wyceny środków trwałych** można uzyskać z obszaru roboczego **Zarządzanie środkami trwałymi** lub ze strony listy **Środek trwały**.

### <a name="related-information"></a>Informacje pokrewne

Można przejść bezpośrednio do strony **Konfiguracja księgi**, **Zapytanie o transakcje na środkach trwałych** i kilku raportów za pomocą łączy w sekcji **Informacje pokrewne** w obszarze roboczym.

### <a name="analytics--all-companies"></a>Analizy — wszystkie firmy

Strona **Analizy** zawiera ważne mierniki o środkach trwałych we wszystkich firmach w systemie. Dostęp do tej karty jest kontrolowany przez uprawnienie zabezpieczeń Wyświetlanie analiz środków trwałych dla wszystkich firm.

W poniższej tabeli pokazano wizualizacje dostępne na każdej stronie raportu.

| Strona raportu            | Wizualizacja        |
|------------------------|----------------------|
| Wyceny środków trwałych | Łączna wartość księgowa netto |
| Wyceny środków trwałych | Wartości księgowe netto wg grup środków trwałych |
| Wyceny środków trwałych | Wartości nabycia |
| Wyceny środków trwałych | Wartości likwidacji |
| Wyceny środków trwałych | Szczegóły dotyczące środków trwałych |
| Mapy wycen        | Łączna wartość księgowa netto |
| Mapy wycen        | Lokalizacje środka trwałego |
| Mapy wycen        | Szczegóły dotyczące środków trwałych |

Aby wyświetlić analizy z danymi, należy najpierw odświeżyć zagregowaną miarę AssetTransactionMeasure na stronie **Magazyn jednostek**.

