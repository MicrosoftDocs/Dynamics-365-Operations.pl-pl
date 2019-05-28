---
title: Usuwanie rozbieżności podczas uzgadniania sum faktur
description: Uzgadnianie sum faktury może pomóc zagwarantować, że rozbieżność sum faktury i kwot oczekiwanych nie wykracza poza dopuszczalne limity tolerancji.
author: abruer
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTotalPriceTolerance
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 63413
ms.assetid: 9ac42457-95b2-4191-ad06-c7e323704466
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 63f4747c13d70d45404069a200124336d6f54947
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1512331"
---
# <a name="resolve-discrepancies-during-invoice-totals-matching"></a>Usuwanie rozbieżności podczas uzgadniania sum faktur

[!include [banner](../includes/banner.md)]

Jednym z typów weryfikację uzgadniania faktur jest uzgadnianie sum faktur. Aby określić, czy system powinien wykonywać uzgadnianie sum faktur, na stronie **Parametry rozrachunków z dostawcami** na karcie **Sprawdzanie poprawności faktur** ustaw dla opcji **Dopasuj sumy faktur** wartość **Tak**. 

Uzgadnianie sum faktury może pomóc zagwarantować, że rozbieżność sum faktury i kwot oczekiwanych nie wykracza poza dopuszczalne limity tolerancji. Na stronie **Szczegóły uzgadniania sum faktur** porównywanych jest sześć sum. Jeśli którakolwiek z nich odbiera od oczekiwanej sumy odpowiedniego zamówienia zakupu, dodawana jest flaga rozbieżności. 

Aby sprawdzić oflagowaną fakturę z rozbieżnościami, w obszarze roboczym **Wprowadzanie faktur od dostawcy** kliknij tytuł **Faktury oczekujące**. Następnie w okienku akcji na karcie **Przegląd** kliknij **Szczegóły uzgadniania**. Jeśli wykryto rozbieżności w uzgadnianiu, ikony ostrzeżenia są wyświetlane obok kwoty faktury. Można wyświetlić szczegółowe informacje o sumach, przeglądając szczegóły uzgadniania sum faktur. 

Po znalezieniu rozbieżności konieczne może być skontaktowanie się z dostawcą, jeśli zachodzi podejrzenie, że informacje na fakturze są niepoprawne. W zależności od umowy z dostawcą można wykonać jedno z następujących działań:

-   Zaakceptowanie różnicy cen i zaksięgowanie faktury z rozbieżnościami. Konfiguracja systemu może wymagać zatwierdzenia przed zaksięgowaniem faktury z rozbieżnościami w uzgadnianiu. W takim przypadku trzeba zatwierdzić rozbieżności uzgadniania i opcjonalnie można wprowadzić komentarz do zatwierdzenia. Następnie można zaksięgować fakturę.
-   Odpowiednie poprawienie kwoty faktury i zaksięgowanie faktury.
-   Zażądanie od dostawcy pełnej zapłaty i nowej, poprawionej faktury.

Aby uzyskać więcej informacji, zobacz [Badanie lub rozwiązywanie wyjątków](tasks/research-resolve-exceptions.md).


