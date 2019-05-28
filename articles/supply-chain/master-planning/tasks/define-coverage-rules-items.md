---
title: Definiowanie reguł zapotrzebowania na towary
description: Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, DefaultDashboard, EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 02aa3b2b7924cdf6317225bfce23f182aa390b8c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565668"
---
# <a name="define-coverage-rules-for-items"></a>Definiowanie reguł zapotrzebowania na towary

[!include [task guide banner](../../includes/task-guide-banner.md)]

Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Procedura przedstawia sposób tworzenia reguł zapotrzebowania i zastępowania ustawień zapotrzebowania dla określonego towaru. Pokazuje także sposób określania domyślnych ustawień zapasów.


## <a name="create-a-coverage-group"></a>Tworzenie grupy zapotrzebowania
1. Przejdź do okna Grupy zapotrzebowania.
2. Kliknij przycisk Nowy.
3. W polu Grupa zapotrzebowania wpisz wartość.
4. W polu Nazwa wpisz wartość.
5. W polu Kalendarz wpisz wartość.
    * Wybierz kalendarz, którego funkcja planowania głównego będzie używać do tworzenia sugestii uzupełniania towarów z tej grupy.  
6. W polu Kod zapotrzebowania wybierz opcję.
    * W tej procedurze wybierz opcję Zapotrzebowanie.  
7. W polu Horyzont czasowy zapotrzebowania (dni) wpisz „90”.
    * W przypadku towarów w tej grupie planowanie główne utworzy sugestie uzupełnienia na maksymalnie 90 dni w przyszłość.  
8. W polu Ilość dni z ujemnym stanem magazynu wpisz „1”.
9. W polu Ilość dni z dodatnim stanem magazynu wpisz „1”.
10. Rozwiń lub zwiń sekcję Inne.
11. W polu Zapas czasu dla przyjęcia dodany do daty zapotrzebowania wpisz „1”.
    * Jeśli na przykład zapas czasu dla przyjęcia jest ustawiony na 1 dzień, a wiersz zamówienia zakupu ma zaplanowane przyjęcie w dniu 15 maja, funkcja planowania głównego wyliczy skorygowaną datę przyjęcia na 16 maja.  
12. W polu Zapas czasu dla rozchodu odjęty od daty zapotrzebowania wpisz „1”.
    * Jeśli na przykład margines bezpieczeństwa jest ustawiony na 1 dzień, a wiersz zamówienia sprzedaży ma zaplanowaną dostawę w dniu 15 maja, funkcja planowania głównego wyliczy skorygowaną datę dostawy na 14 maja.  
13. W polu Zapas czasu dla ponownego zamówienia dodany do czasu realizacji towaru wpisz „1”.
14. Kliknij przycisk Zapisz.

## <a name="create-a-new-product"></a>Tworzenie nowego produktu
1. Przejdź do okna Zwolnione produkty.
2. Kliknij przycisk Nowy.
3. W polu Numer produktu wpisz wartość.
4. W polu Nazwa produktu wpisz wartość.
5. W polu Grupa modeli towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
6. Na liście znajdź i zaznacz odpowiedni rekord.
7. Na liście kliknij łącze w wybranym wierszu.
8. W polu Grupa towarów kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
9. Na liście znajdź i zaznacz odpowiedni rekord.
10. Na liście kliknij łącze w wybranym wierszu.
11. W polu Grupa wymiarów magazynowania kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
12. Na liście znajdź i zaznacz odpowiedni rekord.
13. Na liście kliknij łącze w wybranym wierszu.
14. W polu Grupa wymiarów śledzenia kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
15. Na liście znajdź i zaznacz odpowiedni rekord.
16. Na liście kliknij łącze w wybranym wierszu.
17. Kliknij przycisk OK.

## <a name="setup-default-order-settings"></a>Konfigurowanie domyślnych ustawień zamówienia
1. W okienku akcji kliknij opcję Plan.
2. Kliknij opcję Ustawienia domyślne zamówień.
3. W polu Oddział zakupu wpisz oddział używany jako domyślny podczas tworzenia zamówień zakupu.
4. W polu Oddział zapasów wpisz oddział, w którym towar jest przechowywany.
5. Rozwiń lub zwiń sekcję Zapasy.
6. W polu Wiele ustaw wartość „10”.
7. W polu Min. ilość zamówienia ustaw wartość „10”.
8. W polu Maks. ilość zamówienia ustaw wartość „100”.
9. W polu Standardowa ilość zamówienia ustaw wartość „10”.
10. W polu Czas realizacji zakupu wpisz liczbę.
11. Zaznacz lub wyczyść pole wyboru Dni robocze.
12. Kliknij przycisk Zapisz.
13. W polu Domyślny typ zamówienia zaznacz opcję „Zamówienie zakupu”.
14. Kliknij przycisk Zapisz.
15. Zamknij stronę.
    * Zamknij stronę Ustawienia domyślne zamówień.  

## <a name="add-an-item-to-a-coverage-group"></a>Dodawanie towaru do grupy zapotrzebowania
1. Rozwiń lub zwiń sekcję Plan.
2. W polu Grupa zapotrzebowania kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
3. Na liście znajdź utworzoną przez siebie grupę zapotrzebowania.
4. Na liście kliknij łącze w wybranym wierszu.

## <a name="create-item-coverage-rules"></a>Tworzenie reguł zapotrzebowania na towary
1. W okienku akcji kliknij opcję Plan.
2. Kliknij opcję Zapotrzebowanie na towary.
3. Kliknij przycisk Nowy.
4. Kliknij kartę Ogólne.
5. Zaznacz pole wyboru w nagłówku Zastępowanie ustawień grupy zapotrzebowania.
6. W polu Horyzont czasowy zapotrzebowania (dni) wpisz „60”.
    * Mimo iż towary w grupie zapotrzebowania Zapotrzebowanie są zaplanowane na najbliższe 90 dni, ten towar będzie zaplanowany na najbliższe 60 dni.  
7. W polu Ilość dni z ujemnym stanem magazynu wpisz „2”.
8. W polu Ilość dni z dodatnim stanem magazynu wpisz „2”.
9. Kliknij kartę Czas realizacji.
10. Zaznacz pole wyboru w nagłówku Zakup.
11. W polu Godzina zakupu wpisz „5”.
12. Kliknij przycisk Zapisz.

