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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 5fe6e54b4ebcf6cd611af54e7066a3e39d0e677d
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-number-sequences-by-using-a-wizard"></a>Konfigurowanie sekwencji numeracji za pomocą kreatora

[!include[task guide banner](../../includes/task-guide-banner.md)]

Sekwencje numeracji są używane do generowania czytelnych, unikatowych identyfikatorów dla rekordów danych głównych i rekordów transakcji, które ich wymagają. Rekord transakcji lub danych głównych, który wymaga identyfikatora, odnosi się do odwołania. Aby można było tworzyć nowe rekordy dla odwołania, należy ustawić sekwencję numerów i skojarzyć je z odwołaniem. W tej procedurze pokazano sposób konfigurowania wszystkich wymaganych sekwencji numeracji w tym samym czasie za pomocą kreatora. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.

1. Wybierz kolejno opcje Administrowanie organizacją > Sekwencje numerów > Sekwencje numerów.
2. Kliknij przycisk Generuj.
3. Kliknij przycisk Dalej.
    * Na tej stronie można zmodyfikować kod identyfikacyjny, najniższą wartość i najwyższą wartość. Ponadto można wskazać, czy sekwencja numerów musi być ciągła.   
    * Nie wybieraj opcji Ciągłe, jeśli konieczne jest wstępne przydzielanie numerów w sekwencji numeracji.     Aby dodać segment zakresu do formatu sekwencji numeracji, wybierz format z listy, a następnie kliknij opcję Uwzględnij zakres w formacie.     Aby usunąć segment zakresu z formatu sekwencji numeracji, wybierz format z listy, a następnie kliknij opcję Usuń zakres z formatu.     Aby wykluczyć sekwencję numeracji z automatycznego generowania, wybierz z listy sekwencję numeracji, a następnie kliknij przycisk Usuń.  
4. Kliknij przycisk Dalej.
5. Kliknij przycisk Zakończ.


