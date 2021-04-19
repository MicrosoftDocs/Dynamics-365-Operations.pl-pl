---
title: Konfigurowanie firm przewozowych
description: W tej procedurze opisano sposób konfigurowania firmy przewozowej i definiowania szczegółów, takich jak usługi, tryb wysyłki, metoda płatności za transport, ograniczenia transportu i stawka kosztów wysyłki.
author: ShylaThompson
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSShippingCarrierCustomerAccount,TMSCarrier
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1c292470e6c70af4dfe11bbe324ebcf93438e29d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840468"
---
# <a name="set-up-shipping-carriers"></a>Konfigurowanie firm przewozowych

[!include [banner](../../includes/banner.md)]

W tej procedurze opisano sposób konfigurowania firmy przewozowej i definiowania szczegółów, takich jak usługi, tryb wysyłki, metoda płatności za transport, ograniczenia transportu i stawka kosztów wysyłki. Koordynator transportu może następnie przypisać firmę przewozową do ładunku przychodzącego i wychodzącego.


## <a name="create-a-new-shipping-carrier"></a>Tworzenie nowej firmy przewozowej
1. Wybierz kolejno opcje **Okienko Nawigacji > Moduły > Zarządzanie transportem > Ustawienia > Przewoźnicy > Firmy przewozowe**.
2. Wybierz pozycję **Nowy** w okienku akcji.
3. W polu **Firma przewozowa** wpisz wartość.
4. W polu **Nazwa** wpisz wartość.
5. W polu **Tryb** wybierz opcję z menu rozwijanego.

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a>Wprowadzanie ogólnych informacji o firmie przewozowej
1. Przełącz rozwinięcie sekcji **Przegląd**.
2. Zaznacz lub usuń zaznaczenie pola wyboru **Aktywuj firmę przewozową**.
3. W polu **Konto dostawcy** wybierz opcję z menu rozwijanego. Wybierz konto dostawcy, do którego chcesz przypisać firmę przewozową.  
4. W polu **Typ metody płatności** za transport wybierz opcję. Wybierz opcję **Ręczne**, aby użyć strony Metoda płatności za transport, lub opcję **EDI**, aby zaktualizować metodę płatności na elektroniczną wymianę danych (EDI).  
5. Zaznacz lub usuń zaznaczenie pola wyboru **Aktywuj oceny przewoźników**.

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a>Tworzenie niezbędnych usług dla firmy przewozowej
1. Przełącz rozwinięcie sekcji **Usługi**.
2. Wybierz pozycję **Nowy**.
3. W polu **Usługa przewozowa** wpisz wartość.
4. W polu **Nazwa** wpisz wartość.
5. W polu **Metoda transportu** wybierz opcję z menu rozwijanego.

## <a name="set-up-the-address-for-the-carrier-optional"></a>Konfigurowanie adresu przewoźnika (opcjonalnie)
1. Przełącz rozwinięcie sekcji **Adresy**.
2. Wybierz pozycję **Nowy**.
3. W polu **Nazwa lub opis** wpisz wartość.
4. W polu **Kraj/region** wybierz opcję z menu rozwijanego.
5. W polu **Kod pocztowy** wybierz opcję z menu rozwijanego.
6. W polu **Ulica** wpisz wartość.
7. Kliknij przycisk **OK**.

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a>Konfigurowanie profilu wyznaczania stawek dla przewoźnika
1. Przełącz rozwinięcie sekcji **Profile oceny**.
2. Wybierz pozycję **Nowy**.
3. W polu **Profil oceny** wpisz wartość.
4. W polu **Nazwa** wpisz wartość.
5. W polu **Oddział** wybierz opcję z menu rozwijanego.
6. W polu **Magazyn** wybierz opcję z menu rozwijanego.
7. W polu **Aparat wyznaczania stawki** wybierz opcję z menu rozwijanego. Wybierz aparat wyznaczania stawki zgodny z umową zawartą z przewoźnikiem.  
8. W polu **Główna stawka** wybierz opcję z menu rozwijanego.
9. W polu **Aparat czasu tranzytu** wybierz opcję z menu rozwijanego.
10. Wybierz opcję **Zapisz**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]