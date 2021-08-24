---
title: Wprowadzanie najważniejszych danych faktury do modułu rozrachunków z dostawcami za pomocą arkusza zatwierdzania
description: W tym przewodniku pokazano sposób używania rejestru faktur do tworzenia faktur, a następnie używania arkusza zatwierdzania do aktualizowania kont wydatków.
author: abruer
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransInvoiceRegister, HcmWorkerLookUp, LedgerJournalTransApprove, LedgerJournalTransApproveFetchVouchers, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 72b2d7a5a554f46813fb31991ffb3df30742d01bf168b4180a1096970f60998f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722942"
---
# <a name="key-invoice-data-into-accounts-payable-using-an-approval-journal"></a>Wprowadzanie najważniejszych danych faktury do modułu rozrachunków z dostawcami za pomocą arkusza zatwierdzania

[!include [banner](../../includes/banner.md)]

W tym przewodniku pokazano sposób używania rejestru faktur do tworzenia faktur, a następnie używania arkusza zatwierdzania do aktualizowania kont wydatków.

## <a name="create-and-post-and-invoice"></a>Tworzenie i księgowanie faktury
1. W okienku nawigacji przejdź do **Moduły > Rozrachunki z dostawcami > Faktury > Rejestr faktur**.
2. Wybierz pozycję **Nowy**.
3. Wybierz nazwę rejestru faktur, którego chcesz używać.
4. Kliknij przycisk **Wiersze**, aby otworzyć rejestr i wprowadzić wiersze wydatków.
5. Wybierz dostawcę. Na przykład wprowadź lub wybierz dostawcę `US-104`.
6. W polu **Faktura** wpisz wartość.
7. W polu **Opis** wpisz wartość.
8. W polu **Kredyt** wpisz liczbę.
9. W polu **Zatwierdzone przez** wybierz osobę zatwierdzającą z menu rozwijanego.
10. Wybierz opcję **Zaksięguj**.

## <a name="approve-an-invoice"></a>Zatwierdzanie faktury
1. W okienku nawigacji przejdź do **Moduły > Rozrachunki z dostawcami > Faktury > Zatwierdzenie faktury**.
2. Wybierz pozycję **Nowy**.
3. Wybierz nazwę arkusza zatwierdzania faktur, którego chcesz używać.
4. Wybierz **Wiersze**, a zostanie wyświetlona strona, gdzie będzie można wybrać faktury do zatwierdzenia.
5. Kliknij przycisk **Znajdź załączniki**, aby wyświetlić wszystkie faktury gotowe do zatwierdzenia.
6. Zaznacz utworzoną fakturę, a następnie kliknij przycisk **Wybierz**. Załączniki wybrane powyżej zostaną po zaznaczeniu przeniesione do tej listy.  
7. Kliknij przycisk **OK**.
8. Wybierz **Numer konta**, aby dodać konto wydatków do faktury.
9. Wprowadź numer konta i opuść to pole. Na przykład wpisz `600120`.
10. Wybierz opcję **Zaksięguj**.
11. Wybierz **Załącznik**, aby wyświetlić zapisy, które zostały zaksięgowane. Konto faktur oczekujących na zatwierdzenie zostanie wycofane i zastąpione kontem wydatków rzeczywistych.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]