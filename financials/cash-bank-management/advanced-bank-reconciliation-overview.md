---
title: "Zaawansowanego uzgodnienia konta bankowego — omówienie"
description: "W tym artykule opisano przebieg procesu zaawansowanego uzgadniania konta bankowego. Funkcja zaawansowanego uzgadniania konta bankowego umożliwia importowanie wyciągów bankowych, a następnie ich automatyczne uzgadnianie z poziomu transakcji bankowych."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 22104
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 00f022da597b1de2454e93123de31731c6a65962
ms.openlocfilehash: 20363ef1917f7d0796cb0d5cd8e623c598b5ee01
ms.lasthandoff: 03/31/2017


---

# <a name="advanced-bank-reconciliation-overview"></a>Zaawansowanego uzgodnienia konta bankowego — omówienie

W tym artykule opisano przebieg procesu zaawansowanego uzgadniania konta bankowego. Funkcja zaawansowanego uzgadniania konta bankowego umożliwia importowanie wyciągów bankowych, a następnie ich automatyczne uzgadnianie z poziomu transakcji bankowych.

Funkcja zaawansowanego uzgodnienia konta bankowego pozwala importować wyciągi bankowe. Zaimportowany wyciąg z konta można następnie automatycznie uzgodnić z poziomu transakcji bankowych. Poniżej przedstawiono kroki w procesie zaawansowanego uzgadniania konta bankowego

1.  Konfigurowanie importu wyciągu bankowego.
    -   Importowanie wyciągów bankowych za pośrednictwem struktury danych jednostki.
    -   Trzy typowe formaty wyciągów bankowych są wbudowane: ISO20022, BAI2, i MT940.
    -   Funkcję można rozszerzyć na dowolny format.

2.  Należy ustawić kolejność na potrzeby zaawansowanego uzgadniania konta bankowego i zdefiniować reguł uzgadniania wyciągów bankowych.
    -   Reguły uzgadniania wyciągów jest zestawem kryteriów, które są używane do filtrowania wierszy wyciągu bankowego i Microsoft Dynamics 365 dla wierszy transakcji bankowych operacje podczas procesu uzgadniania. W zależności od Twojego praktyki prowadzenia działalności można skonfigurować więcej niż jedną regułę dopasowywania do automatyzacji i optymalizowaniu procesu pojednania.

3.  Uzgadnianie wyciągów bankowych 365 Dynamics dla transakcji bankowych operacji.
    -   Automatyczne dopasowywanie i tworzenie arkuszy uzgadniania konta.
    -   Przejrzeć wyciągi bankowe i 365 Dynamics dla transakcji bankowych operacje obok siebie.
    -   Automatyczne księgowanie Dynamics 365 dla transakcji bankowych operacji, jeśli są wyświetlane na wyciągu bankowym, ale nie są wyświetlane w usłudze Dynamics 365 dla operacji.
    -   Generowanie wyciągu uzgodnienia.




