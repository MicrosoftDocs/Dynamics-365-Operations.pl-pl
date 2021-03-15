---
title: Tworzenie i eksport płatności dla dostawcy przy użyciu formatu płatności ISO20022
description: W tej procedurze pokazano sposób tworzenia wierszy w arkuszu płatności dostawcy oraz generowania pliku płatności dla dostawcy na przykładzie polecenia przelewu ISO2022.
author: mrolecki
manager: AnnBe
ms.date: 01/17/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym, SysQueryForm, VendPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1df738e3925dc23e7723d93f33acf6a9d811b113
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4964548"
---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a>Tworzenie i eksportowanie płatności dla dostawcy przy użyciu formatu płatności ISO20022

[!include [banner](../../includes/banner.md)]

W tym temacie pokazano sposób tworzenia wierszy w arkuszu płatności dostawcy oraz generowania pliku płatności dla dostawcy na przykładzie polecenia przelewu ISO2022.

Jest to piąta z pięciu procedur, które razem ilustrują proces płatności dostawcom przy użyciu konfiguracji raportowania elektronicznego. W tym przykładzie użyj danych demonstracyjnych DEMF.

## <a name="example"></a>Przykład

1.    Wybierz kolejno opcje **Rozrachunki z dostawcami > Płatności > Arkusz płatności**.
2.    Kliknij przycisk **Nowy**.
3.    W polu **Nazwa** wprowadź lub wybierz wartość.
4.    Kliknij kolejno pozycje **Wiersze > Propozycja płatności -> Utwórz propozycję płatności**.
5.    Rozwiń sekcję **Rekordy do uwzględnienia**.
6.    Kliknij przycisk **Filtr**.
7.    Na liście zaznacz wiersz dla **tabeli Dostawcy** i **pola Konto dostawcy**.
8.    W polu **Kryteria** wprowadź lub wybierz wartość. Można stosować dowolne kryteria w celu wybrania transakcji z dostawcą, które mają zostać opłacone. W tym przykładzie zostanie użyte kryterium DE-001 jako konto dostawcy.
12.    Kliknij przycisk **OK**.
13.    Kliknij przycisk **OK**.
14.    Kliknij opcję **Utwórz płatności**.
15. Generowanie pliku płatności ISO20022.
    1.    Kliknij opcję **Generuj płatności**.
    2.    W polu **Metoda płatności** wprowadź lub wybierz wartość.
    3.    W polu **Nazwa pliku** wpisz wartość. Na przykład z powodu płatności EUR wygenerowany plik będzie zgodny z SEPA. Polecenie przelewu ISO20022 i inne formaty płatności dostawców mogą też służyć do generowania płatności w innych walutach.
    4.    W polu **Konto bankowe** wprowadź lub wybierz wartość.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]