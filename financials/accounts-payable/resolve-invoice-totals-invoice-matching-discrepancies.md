---
title: "Usuwanie rozbieżności wykrytych podczas uzgadniania faktur"
description: 
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 63413
ms.assetid: 9ac42457-95b2-4191-ad06-c7e323704466
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 1fd606817b06a05b9abaaedf20ea9872bd7edd5d
ms.openlocfilehash: a54b05bba2549a42f24b8425c9ee418c576d056a
ms.lasthandoff: 03/31/2017


---

# <a name="resolve-discrepancies-during-invoice-totals-matching"></a>Usuwanie rozbieżności wykrytych podczas uzgadniania faktur



Jednym z typów weryfikację uzgadniania faktur jest uzgadnianie sum faktur. Aby określić, czy system powinien wykonywać uzgadnianie sum faktur, na stronie **Parametry rozrachunków z dostawcami** na karcie **Sprawdzanie poprawności faktur** ustaw dla opcji **Dopasuj sumy faktur** wartość **Tak**. 

Uzgadnianie sum faktury może pomóc zagwarantować, że rozbieżność sum faktury i kwot oczekiwanych nie wykracza poza dopuszczalne limity tolerancji. Na stronie **Szczegóły uzgadniania sum faktur** porównywanych jest sześć sum. Jeśli którakolwiek z nich odbiera od oczekiwanej sumy odpowiedniego zamówienia zakupu, dodawana jest flaga rozbieżności. 

Aby sprawdzić oflagowaną fakturę z rozbieżnościami, w obszarze roboczym **Wprowadzanie faktur od dostawcy** kliknij tytuł **Faktury oczekujące**. Następnie w okienku akcji na karcie **Przegląd** kliknij **Szczegóły uzgadniania**. Jeśli wykryto rozbieżności w uzgadnianiu, ikony ostrzeżenia są wyświetlane obok kwoty faktury. Można wyświetlić szczegółowe informacje o sumach, przeglądając szczegóły uzgadniania sum faktur. 

Po znalezieniu rozbieżności konieczne może być skontaktowanie się z dostawcą, jeśli zachodzi podejrzenie, że informacje na fakturze są niepoprawne. W zależności od umowy z dostawcą można wykonać jedno z następujących działań:

-   Zaakceptowanie różnicy cen i zaksięgowanie faktury z rozbieżnościami. Konfiguracja systemu może wymagać zatwierdzenia przed zaksięgowaniem faktury z rozbieżnościami w uzgadnianiu. W takim przypadku trzeba zatwierdzić rozbieżności uzgadniania i opcjonalnie można wprowadzić komentarz do zatwierdzenia. Następnie można zaksięgować fakturę.
-   Odpowiednie poprawienie kwoty faktury i zaksięgowanie faktury.
-   Zażądanie od dostawcy pełnej zapłaty i nowej, poprawionej faktury.



