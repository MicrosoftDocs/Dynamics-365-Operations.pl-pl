---
title: Konfigurowanie numeracji za pomocą kreatora
description: W tym temacie pokazano sposób konfigurowania wszystkich wymaganych sekwencji numeracji w tym samym czasie za pomocą kreatora.
author: sericks007
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceWizard
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cd335f73b2851352dce1eb36c5e5e6838f8611c8ed9fa8cb65fd1c826530f857
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6749491"
---
# <a name="set-up-number-sequences-using-a-wizard"></a>Konfigurowanie numeracji za pomocą kreatora

[!include [banner](../../includes/banner.md)]

Sekwencje numeracji są używane do generowania czytelnych, unikatowych identyfikatorów dla rekordów danych głównych i rekordów transakcji, które ich wymagają. Rekord transakcji lub danych głównych, który wymaga identyfikatora, odnosi się do odwołania. Aby można było tworzyć nowe rekordy dla odwołania, należy ustawić sekwencję numerów i skojarzyć je z odwołaniem. W tym temacie pokazano sposób konfigurowania wszystkich wymaganych sekwencji numeracji w tym samym czasie za pomocą kreatora. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.

1. Otwórz **Nawigacja > Moduły > Administrowanie organizacją > Sekwencje numerów > Sekwencje numerów**.
2. Wybierz **Generuj**.
3. Wybierz pozycję **Następny**.

   - Na tej stronie można zmodyfikować kod identyfikacyjny, najniższą wartość i najwyższą wartość. Ponadto można wskazać, czy sekwencja numerów musi być ciągła.   
   - Nie wybieraj opcji **Ciągłe**, jeśli konieczne jest wstępne przydzielanie numerów w sekwencji numeracji. Aby dodać segment zakresu do formatu sekwencji numeracji, wybierz format z listy, a następnie wybierz **Uwzględnij zakres w formacie**. Aby usunąć segment zakresu z formatu sekwencji numerów, wybierz format z listy, a następnie kliknij opcję **Usuń zakres z formatu**. Aby wykluczyć sekwencję numerów z automatycznego generowania, wybierz z listy sekwencję numerów, a następnie wybierz **Usuń**.  

4. Wybierz pozycję **Następny**.
5. Wybierz **Zakończ**.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]