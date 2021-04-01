---
title: Zaawansowanego uzgodnienia konta bankowego — omówienie
description: W tym artykule opisano przebieg procesu zaawansowanego uzgadniania konta bankowego. Funkcja zaawansowanego uzgadniania konta bankowego umożliwia importowanie wyciągów bankowych, a następnie ich automatyczne uzgadnianie z poziomu transakcji bankowych.
author: panolte
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: roschlom
ms.custom: 22104
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1f85ece0b25237c194777b41566860c49d4b9d39
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5258215"
---
# <a name="advanced-bank-reconciliation-overview"></a>Zaawansowanego uzgodnienia konta bankowego — omówienie

[!include [banner](../includes/banner.md)]

W tym artykule opisano przebieg procesu zaawansowanego uzgadniania konta bankowego. Funkcja zaawansowanego uzgadniania konta bankowego umożliwia importowanie wyciągów bankowych, a następnie ich automatyczne uzgadnianie z poziomu transakcji bankowych.

Funkcja zaawansowanego uzgodnienia konta bankowego pozwala importować wyciągi bankowe. Zaimportowany wyciąg z konta można następnie automatycznie uzgodnić z poziomu transakcji bankowych. Poniżej przedstawiono kroki w procesie zaawansowanego uzgadniania konta bankowego

1.  Konfigurowanie importu wyciągu bankowego.
    -   Importowanie wyciągów bankowych za pośrednictwem struktury danych jednostki.
    -   Trzy typowe formaty wyciągów bankowych są wbudowane: ISO20022, BAI2, i MT940.
    -   Funkcję można rozszerzyć na dowolny format.

2.  Należy ustawić kolejność na potrzeby zaawansowanego uzgadniania konta bankowego i zdefiniować reguł uzgadniania wyciągów bankowych.
    -   Reguły uzgadniania wyciągów to zestaw kryteriów, które są używane do filtrowania podczas procesu uzgadniania wierszy wyciągu bankowego z wierszami transakcji bankowych w Microsoft Dynamics 365 Finance. W zależności od praktyk biznesowych klienta można skonfigurować więcej niż jedną regułę uzgadniania i zautomatyzować oraz zoptymalizować proces uzgadniania.

3.  Uzgadnianie wyciągów bankowych z transakcjami bankowymi w programie Finance.
    -   Automatyczne dopasowywanie i tworzenie arkuszy uzgadniania konta.
    -   Bezpośrednie porównywanie wyciągów bankowych z transakcjami bankowymi w aplikacji Finance.
    -   Automatyczne księgowanie transakcji bankowych w Finance, jeśli pojawiają się na wyciągu bankowym, ale nie ma ich w aplikacji Finance.
    -   Generowanie wyciągu uzgodnienia.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]