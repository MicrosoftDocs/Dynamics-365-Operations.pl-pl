---
title: Deponowanie płatności odbiorców
description: Wpłacanie płatności od odbiorców.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransCustPaym, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: afbf74d1cf3dc87e97dda0873115b5c7fa49ca3d
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834470"
---
# <a name="deposit-customer-payments"></a>Deponowanie płatności odbiorców

[!include [task guide banner](../../includes/task-guide-banner.md)]

Wpłacanie płatności od odbiorców. W zadaniu wykorzystano firmę demonstracyjną USMF.

1. Wybierz kolejno opcje Rozrachunki z odbiorcami > Płatności > Arkusz płatności.
2. Kliknij przycisk Nowy.
3. W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Wybierz arkusz płatności. 
5. Kliknij przycisk Wiersze.
6. W polu konto zaznacz odbiorcę, dla którego rejestrujesz płatność.
7. W polu Kredyt wprowadź kwotę płatności.
    * Można wybrać opcję niewypełniania pola, a obliczania jego wartości przez system po zaznaczeniu opłaconych faktur.  
8. W polu Odwołanie do płatności wpisz wartość.
    * Odwołaniem do płatności może być numeru czeku z wprowadzanej płatności. Odwołanie do płatności jest wymagane w celu uwzględnienia płatności na dokumencie wpłaty.  
9. Zaznacz opcję Użyj dokumentu wpłaty.
    * Jeśli płatność ma być uwzględniona we wpłacie, zmień to ustawienie na Tak.  
10. Kliknij przycisk Nowy.
11. W polu Konto wybierz odbiorcę dla następnej płatności.
12. W polu Kredyt wprowadź kwotę płatności.
13. W polu Odwołanie do płatności wpisz wartość.
14. Zaznacz opcję Użyj dokumentu wpłaty.
15. Kliknij przycisk Księguj.
    * Aby można było wygenerować dokument wpłaty, płatności być zaksięgowane. Ma to na celu zagwarantowanie, że płatności nie zmienią się po wygenerowaniu dokumentu wpłaty.  
16. Kliknij przycisk Funkcje.
17. Kliknij opcję Dokument wpłaty.
18. Kliknij przycisk OK.
    * Pierwsza strona jest używana do utworzenia dokumentu wpłaty.  
19. Kliknij przycisk OK.
    * Drugim krokiem jest wydrukowanie dokumentu wpłaty, ale ten krok nie jest wymagany.  

