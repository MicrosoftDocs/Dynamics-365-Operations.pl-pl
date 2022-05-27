---
title: Deponowanie płatności odbiorców
description: Wpłacanie płatności od odbiorców.
author: ShivamPandey-msft
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransCustPaym, CustTableLookup
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8ed692d9c82fd496e31258a70415db1838d99313
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/05/2022
ms.locfileid: "8714041"
---
# <a name="deposit-customer-payments"></a>Deponowanie płatności odbiorców

[!include [banner](../../includes/banner.md)]

Wpłacanie płatności od odbiorców. W zadaniu wykorzystano firmę demonstracyjną USMF.

1. Wybierz kolejno **Okienko nawigacji > Moduły > Rozrachunki z dostawcami > Płatności > Arkusz płatności**.
2. Wybierz pozycję **Nowy**.
3. W polu **Nazwa** wybierz opcję **CustPay** z menu rozwijanego.
4. Wybierz **Linie**.
5. W polu **Konto** zaznacz odbiorcę, dla którego rejestrujesz płatność.
6. W polu **Kredyt** wprowadź kwotę płatności. Można wybrać opcję niewypełniania pola, a obliczania jego wartości przez system po zaznaczeniu opłaconych faktur.  
7. W polu **Odwołanie do płatności** wpisz wartość. Odwołaniem do płatności może być numeru czeku z wprowadzanej płatności. Odwołanie do płatności jest wymagane w celu uwzględnienia płatności na dokumencie wpłaty.  
8. Zaznacz opcję Użyj dokumentu wpłaty. Jeśli płatność ma być uwzględniona we wpłacie, zmień to ustawienie na Tak.  
9. Wybierz pozycję **Nowy**.
10. W polu **Konto** wybierz odbiorcę dla następnej płatności.
11. W polu **Kredyt** wprowadź kwotę płatności.
12. W polu **Odwołanie do płatności** wpisz wartość.
13. Zaznacz opcję **Użyj dokumentu wpłaty**.
14. Wybierz opcję **Zaksięguj**. Aby można było wygenerować dokument wpłaty, płatności być zaksięgowane. Ma to na celu zagwarantowanie, że płatności nie zmienią się po wygenerowaniu dokumentu wpłaty.  
15. Wybierz **Funkcje**.
16. Wybierz **Dokument wpłaty**.
17. Kliknij przycisk **OK**. Pierwsza strona jest używana do utworzenia dokumentu wpłaty.  
18. Kliknij przycisk **OK**. Drugim krokiem jest wydrukowanie dokumentu wpłaty, ale ten krok nie jest wymagany.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
