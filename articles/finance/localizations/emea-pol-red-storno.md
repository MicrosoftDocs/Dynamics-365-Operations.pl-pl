---
title: Aktywowanie stornowania dla Polski
description: Ten temat zawiera informacje o funkcji stornowania dla Polski.
author: ShylaThompson
ms.date: 09/11/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Poland
ms.author: roschlom
ms.dyn365.ops.version: AX 7.0.1
ms.search.validFrom: 2016-05-31
ms.openlocfilehash: 017a1c55cb1af21163ab6d96a8692fc87822d880
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832684"
---
# <a name="activate-storno-accounting-for-poland"></a>Aktywowanie stornowania dla Polski

[!include [banner](../includes/banner.md)]

Niniejsze procedury służą do konfigurowania operacji stornowania. Stornowanie polega na zmianie znaku kwot w celu wycofania błędnych oryginalnych transakcji. Na przykład następujące transakcje są zarejestrowane niepoprawnie.

|opis        | Strona debetowa |Strona kredytowa  |
|-------------------|-------|--------|
|Przychód ze sprzedaży      |       |100,00  |
|Rozrachunki z odbiorcami|100,00 |        |

Aby wycofać transakcje i księgować transakcje wycofywania jako transakcje storno, należy wprowadzić następujące informacje.

|opis        | Strona debetowa  |Strona kredytowa   |
|-------------------|--------|---------|
|Przychód ze sprzedaży      |        |-100,00  |
|Rozrachunki z odbiorcami|-100,00 |         |

Każda transakcja wycofywania pojawia się w tej samej kolumnie debetowej lub kredytowej co oryginalna transakcja. Zachowanie kwot w oryginalnych kolumnach i zmiana znaku kwot powoduje skuteczne „wyzerowanie” oryginalnej transakcji.

Po wykonaniu poniższej procedury zostanie utworzona transakcja, która automatycznie wycofuje (stornuje) transakcje.

## <a name="activate-storno-accounting"></a>Uaktywnienie stornowania
Należy aktywować stornowanie w module Księga główna, zanim będzie możliwe konfigurowanie parametrów stornowania w dowolnym innym module.

1. Kliknij kolejno opcje **Księga główna** > **Ustawienia** > **Parametry księgi głównej**.
2. W obszarze **Księga** na skróconej karcie **Reguły księgowania** w grupie pól **Wycofanie transakcji** ustaw opcję **Korekta** na **Tak**.

## <a name="set-up-storno-accounting"></a>Konfigurowanie stornowania
Po aktywowaniu stornowania można skonfigurować parametry w modułach aplikacji. Parametry specyficzne dla modułu zazwyczaj używają stornowania domyślnie dla różnych procesów w module. Można zmieniać domyślne ustawienie wyświetlane na stronie. Jednak ustawienie nie jest widoczne na wszystkich stronach. Niektóre strony zawsze używają wartości domyślnej podczas przetwarzania i nie można zmienić tego ustawienia.

### <a name="set-up-storno-accounting-in-accounts-payable"></a>Ustawianie stornowania w module Rozrachunki z dostawcami
Na stronie **Parametry modułu rozrachunków z dostawcami** w obszarze **Faktura** w opcji **Faktura korygująca z czerwonym stornem** ustaw wartość **Tak**. Domyślnie faktury korygujące teraz są księgowane jako transakcje stornowania.

### <a name="set-up-storno-accounting-in-accounts-receivable"></a>Ustawianie stornowania w module Rozrachunki z odbiorcami
1. Przejdź do strony **Parametry modułu rozrachunków z odbiorcami**.
2. W obszarze **Aktualizacje** w grupie pól **Faktura zaliczkowa** w opcji **Faktura korygująca z czerwonym stornem** ustaw wartość **Tak**. Domyślni, faktury korygujące dla faktur zaliczkowych są teraz księgowane jako transakcje stornowania.
3. W opcji **Wycofanie jako korekta** ustaw wartość **Tak**. Domyślnie wycofania dla faktur korygujących są teraz księgowane jako transakcje stornowania.
4. W grupie pól **Faktura** w opcji **Faktura korygująca z czerwonym stornem** ustaw wartość to **Tak**. Domyślnie faktury korygujące dla faktur są teraz księgowane jako transakcje stornowania.

### <a name="set-up-storno-accounting-in-inventory-and-warehouse-management"></a>Ustawianie stornowania w module Zarządzanie zapasami i magazynem
1. Przejdź do strony **Parametry modułu Zarządzanie zapasami i magazynem**.
2. W obszarze **Ogólne** w grupie pól **Korekta** w opcji **Korekta zapasów — korekta** ustaw wartość **Tak**. Domyślnie korekty zapasów są teraz księgowane jako transakcje stornowania.

### <a name="set-up-storno-accounting-in-project-management-and-accounting"></a>Ustawianie stornowania w module Zarządzanie projektami i ich księgowanie
1. Przejdź do strony **Parametry modułu Zarządzanie projektami i ich księgowanie**.
2. W obszarze **Ogólne** w grupie pól **Korekta** w opcji **Korekta transakcji projektów — korekta** ustaw wartość **Tak**. Domyślnie korekty transakcji projektów są teraz księgowane jako transakcje stornowania.
3. W obszarze **Arkusze** w grupie pól **Księgowanie w księdze** w opcji **Transakcje ujemne — korekta** ustaw wartość **Tak**. Domyślnie wpisy w arkuszu projektów zawierające ujemną kwotę kosztów są teraz księgowane jako transakcje stornowania.

### <a name="create-an-invoice-storno-credit-note"></a>Tworzenie faktury korygującej w celu wystornowania faktury   
 1. Dla potwierdzonego zamówienia zakupu w okienku akcji kliknij opcję **Faktura**.  
 2. Kliknij opcję **Faktura**.  
 3. W okienku akcji kliknij opcję **Domyślnie z: Ilość z dokumentu przyjęcia produktów**.  
 4. W polu **Domyślna ilość dla wierszy** zaznacz opcję.  
 5. Kliknij przycisk **OK**.  
 6. W opcji **Korekta z czerwonym stornem** ustaw wartość **Tak**.  
 7. W polu **Numer** wpisz wartość.  
 8. W polu **Data faktury** wprowadź datę.  
 9. Kliknij przycisk **Księguj**.  



[!INCLUDE[footer-include](../../includes/footer-banner.md)]