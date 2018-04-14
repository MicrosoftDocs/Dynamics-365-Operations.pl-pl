--- 
title: "Konfigurowanie sekwencji numeracji za pomocą kreatora"
description: "Sekwencje numeracji są używane do generowania czytelnych, unikatowych identyfikatorów dla rekordów danych głównych i rekordów transakcji, które ich wymagają."
author: sericks007
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 96c1bc711350b447611977c3f2070fbc08fbae0f
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-number-sequences-by-using-a-wizard"></a>Konfigurowanie sekwencji numeracji za pomocą kreatora

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Sekwencje numeracji są używane do generowania czytelnych, unikatowych identyfikatorów dla rekordów danych głównych i rekordów transakcji, które ich wymagają. Rekord transakcji lub danych głównych, który wymaga identyfikatora, odnosi się do odwołania. Aby można było tworzyć nowe rekordy dla odwołania, należy ustawić sekwencję numerów i skojarzyć je z odwołaniem. W tej procedurze pokazano sposób konfigurowania wszystkich wymaganych sekwencji numeracji w tym samym czasie za pomocą kreatora. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.

1. Wybierz kolejno opcje Administrowanie organizacją > Sekwencje numerów > Sekwencje numerów.
2. Kliknij przycisk Generuj.
3. Kliknij przycisk Dalej.
    * Na tej stronie można zmodyfikować kod identyfikacyjny, najniższą wartość i najwyższą wartość. Ponadto można wskazać, czy sekwencja numerów musi być ciągła.   
    * Nie wybieraj opcji Ciągłe, jeśli konieczne jest wstępne przydzielanie numerów w sekwencji numeracji.     Aby dodać segment zakresu do formatu sekwencji numeracji, wybierz format z listy, a następnie kliknij opcję Uwzględnij zakres w formacie.     Aby usunąć segment zakresu z formatu sekwencji numeracji, wybierz format z listy, a następnie kliknij opcję Usuń zakres z formatu.     Aby wykluczyć sekwencję numeracji z automatycznego generowania, wybierz z listy sekwencję numeracji, a następnie kliknij przycisk Usuń.  
4. Kliknij przycisk Dalej.
5. Kliknij przycisk Zakończ.


