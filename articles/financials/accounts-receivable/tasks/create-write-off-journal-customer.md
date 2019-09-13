---
title: Tworzenie arkusza odpisów dla odbiorcy
description: W tym przewodniku po zadaniach zostanie pokazany sposób konfigurowania parametrów odpisów i następnie transakcji odpisu ze stron Windykacja, Otwarte faktury odbiorcy i Odbiorca.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, CustPosting, DefaultDashboard, CustCollectionsPoolsListPage, CustWriteOff, LedgerJournalTable, LedgerJournalTransDaily, CustCollections, CustOpenInvoicesListPage, CustTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2422f0a9d168daa76d105099c8b7455c97f92125
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916330"
---
# <a name="create-a-write-off-journal-for-a-customer"></a>Tworzenie arkusza odpisów dla odbiorcy

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tym przewodniku po zadaniach zostanie pokazany sposób konfigurowania parametrów odpisów i następnie transakcji odpisu ze stron Windykacja, Otwarte faktury odbiorcy i Odbiorca. W zadaniu wykorzystano firmę demonstracyjną USMF.


## <a name="set-up-the-write-off-parameters"></a>Konfigurowanie parametrów odpisów
1. Przejdź do **Okienko nawigacji > Moduły > Kredyty i windykacja > Ustawienia > Parametry modułu rozrachunków z odbiorcami**.
2. Kliknij kartę **Windykacja**.
3. Rozwiń lub zwiń sekcję **Odpisz**.
    - **Arkusz odpisów** jest arkuszem finansowym, który będzie zawierał transakcje odpisu utworzone przez Ciebie.  
    - Do każdego odpisu można dołączyć kod przyczyny. To domyślne ustawienie można zastąpić podczas dokonywania odpisu.  
    - Ustaw wartość Tak w **Oddziel podatek**, aby w odpisie oddzielić podatek od oryginalnej transakcji.  
4. Zamknij stronę.
5. Wybierz kolejno opcje **Kredyty i windykacja > Ustawienia > Profile księgowania odbiorców**. Konto odpisu będzie używane jako konto wydatków lub rezerwacji korekt w arkuszu finansowym.
6. Zamknij stronę.

## <a name="write-off-a-customer-balance-from-the-aged-balances-page"></a>Odpisywanie salda odbiorcy ze strony wiekowanych sald
1. Wybierz kolejno opcje **Kredyty i windykacja > Windykacja > Wiekowane salda**.
2. Zaznacz wiersz odbiorcy, dla którego ma zostać dokonany odpis. Na przykład zaznacz wiersz z firmą Birch Company.
3. W **okienku akcji** kliknij pozycję **Windykacja**.
4. Kliknij opcję **Odpisz**.
5. Kliknij przycisk **OK**.
6. Zamknij stronę.
7. Otwórz **Okienko nawigacji > Moduły > Księga główna > Wpisy w arkuszu > Arkusze finansowe**.
8. Wybierz numer partii arkuszy z arkuszem, który zawiera odpis. Jest tworzony jeden wiersz w celu wystornowania salda odbiorcy. Jeden lub więcej wierszy jest tworzonych w celu zaksięgowania odpisu na koncie odpisów.  
9. Zamknij stronę.
10. Zamknij stronę.

## <a name="write-off-transactions-from-the-collections-form"></a>Odpisywanie transakcji z formularza windykacji
1. Wybierz kolejno opcje **Kredyty i windykacja > Windykacja > Wiekowane salda**.
2. Zaznacz nazwę odbiorcy mającego transakcje, które chcesz odpisać. Na przykład wybierz Cave Wholesales (US-004).
3. Zaznacz wiersz pierwszej transakcji.
4. Zaznacz wiersz drugiej transakcji.
5. Kliknij opcję **Odpisz**.
6. W polu **Komentarz dotyczący przyczyny** wpisz „Prawdopodobnie nieściągalne długi”.
7. Kliknij przycisk **OK**.
8. Zamknij stronę.
9. Zamknij stronę.
10. Wybierz kolejno opcje **Księga główna > Wpisy w arkuszu > Arkusze finansowe**.
11. Wybierz numer partii arkuszy z arkuszem, który zawiera odpis. Jest tworzony jeden wiersz w celu wystornowania salda odbiorcy. Jeden lub więcej wierszy jest tworzonych w celu zaksięgowania odpisu na koncie odpisów.  
12. Zamknij stronę.
13. Zamknij stronę.

## <a name="write-off-an-invoice-from-the-open-customers-invoices-page"></a>Odpisywanie faktury ze strony Otwarte faktury odbiorców
1. W okienku nawigacji otwórz **Moduły > Rozrachunki z odbiorcami > Faktury > Otwarte faktury dla odbiorców**.
2. Zaznacz wiersz faktury. Na przykład zaznacz wiersz faktury CIV-000667.
3. W **okienku akcji** kliknij pozycję **Faktura**.
4. Kliknij opcję **Odpisz**.
5. Kliknij przycisk **OK**.
6. Zamknij stronę.

## <a name="write-off-a-customer-balance-from-the-customer-page"></a>Odpisywanie salda odbiorcy ze strony odbiorcy
1. Wybierz kolejno opcje **Rozrachunki z odbiorcami > Odbiorcy > Wszyscy odbiorcy**.
2. Umożliwia wybór konta odbiorcy. Wybierz na przykład US-001 (Contoso Retail San Diego).
3. W **okienku akcji** kliknij pozycję **Windykacja**.
4. Kliknij opcję **Odpisz**.
5. Kliknij przycisk **OK**.
6. Zamknij stronę.

