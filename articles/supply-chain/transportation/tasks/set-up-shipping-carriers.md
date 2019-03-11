---
title: Konfigurowanie firm przewozowych
description: W tej procedurze opisano sposób konfigurowania firmy przewozowej i definiowania szczegółów, takich jak usługi, tryb wysyłki, metoda płatności za transport, ograniczenia transportu i stawka kosztów wysyłki.
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6c5ac13d17c97f20ee79e7faf57c570f02158424
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "314493"
---
# <a name="set-up-shipping-carriers"></a>Konfigurowanie firm przewozowych

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze opisano sposób konfigurowania firmy przewozowej i definiowania szczegółów, takich jak usługi, tryb wysyłki, metoda płatności za transport, ograniczenia transportu i stawka kosztów wysyłki. Koordynator transportu może następnie przypisać firmę przewozową do ładunku przychodzącego i wychodzącego.


## <a name="create-a-new-shipping-carrier"></a>Tworzenie nowej firmy przewozowej
1. Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Przewoźnicy > Firmy przewozowe.
2. Kliknij przycisk Nowy.
3. W polu Firma przewozowa wpisz wartość.
4. W polu Nazwa wpisz wartość.
5. W polu Tryb kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
6. Na liście znajdź i zaznacz odpowiedni rekord.
7. Na liście kliknij łącze w wybranym wierszu.

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a>Wprowadzanie ogólnych informacji o firmie przewozowej
1. Przełącz rozwinięcie sekcji Przegląd.
2. Zaznacz lub usuń zaznaczenie pola wyboru Aktywuj firmę przewozową.
3. W polu Dostawca kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Wybierz konto dostawcy, do którego chcesz przypisać firmę przewozową.  
4. Na liście znajdź i zaznacz odpowiedni rekord.
5. Na liście kliknij łącze w wybranym wierszu.
6. W polu Typ metody płatności za transport wybierz opcję.
    * Wybierz opcję Ręczne, aby użyć strony Metoda płatności za transport, lub opcję EDI, aby zaktualizować metodę płatności na elektroniczną wymianę danych (EDI).  
7. Zaznacz lub usuń zaznaczenie pola wyboru Aktywuj oceny przewoźników.

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a>Tworzenie niezbędnych usług dla firmy przewozowej
1. Przełącz rozwinięcie sekcji Usługi.
2. Kliknij przycisk Nowy.
3. Na liście oznacz wybrany wiersz.
4. W polu Usługa przewozowa wpisz wartość.
5. W polu Nazwa wpisz wartość.
6. W polu Metoda transportu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
7. Na liście znajdź i zaznacz odpowiedni rekord.
8. Na liście kliknij łącze w wybranym wierszu.

## <a name="set-up-the-address-for-the-carrier-optional"></a>Konfigurowanie adresu przewoźnika (opcjonalnie)
1. Przełącz rozwinięcie sekcji Adresy.
2. Kliknij przycisk Nowy.
3. W polu Nazwa lub opis wpisz wartość.
4. W polu Kraj/region kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. Na liście kliknij łącze w wybranym wierszu.
6. W polu Kod pocztowy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
7. Na liście znajdź i zaznacz odpowiedni rekord.
8. Na liście kliknij łącze w wybranym wierszu.
9. W polu Ulica wpisz wartość.
10. Kliknij przycisk OK.

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a>Konfigurowanie profilu wyznaczania stawek dla przewoźnika
1. Przełącz rozwinięcie sekcji Profile oceny.
2. Kliknij przycisk Nowy.
3. Na liście oznacz wybrany wiersz.
4. W polu Profil oceny wpisz wartość.
5. W polu Nazwa wpisz wartość.
6. W polu Oddział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
7. Na liście znajdź i zaznacz odpowiedni rekord.
8. Na liście kliknij łącze w wybranym wierszu.
9. W polu Magazyn kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
10. Na liście znajdź i zaznacz odpowiedni rekord.
11. Na liście kliknij łącze w wybranym wierszu.
12. W polu Aparat wyznaczania stawki kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Wybierz aparat wyznaczania stawki zgodny z umową zawartą z przewoźnikiem.  
13. Na liście znajdź i zaznacz odpowiedni rekord.
14. Na liście kliknij łącze w wybranym wierszu.
15. W polu Główna stawka kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
16. Na liście znajdź i zaznacz odpowiedni rekord.
17. Na liście kliknij łącze w wybranym wierszu.
18. W polu Aparat czasu tranzytu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
19. Na liście kliknij łącze w wybranym wierszu.
20. Kliknij przycisk Zapisz.

