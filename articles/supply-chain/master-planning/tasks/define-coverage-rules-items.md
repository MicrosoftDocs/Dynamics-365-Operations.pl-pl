---
title: Definiowanie reguł zapotrzebowania na towary
description: Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.
author: ShylaThompson
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqGroup, DefaultDashboard, EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ff2d83a01f366517502bfc5c885b6f963bd945ca
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829720"
---
# <a name="define-coverage-rules-for-items"></a>Definiowanie reguł zapotrzebowania na towary

[!include [banner](../../includes/banner.md)]

Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Procedura przedstawia sposób tworzenia reguł zapotrzebowania i zastępowania ustawień zapotrzebowania dla określonego towaru. Pokazuje także sposób określania domyślnych ustawień zapasów.


## <a name="create-a-coverage-group"></a>Tworzenie grupy zapotrzebowania
1. Przejdź do **okienka nawigacji > Moduły > Planowanie główne > Ustawienia > Grupy zapotrzebowania**.
2. Kliknij przycisk **Nowy**.
3. W polu **Grupa zapotrzebowania** wpisz wartość.
4. W polu **Nazwa** wpisz wartość.
5. W polu **Kalendarz** wpisz wartość. Wybierz kalendarz, którego funkcja planowania głównego będzie używać do tworzenia sugestii uzupełniania towarów z tej grupy.  
6. W polu **Kod zapotrzebowania** wybierz opcję. W tej procedurze wybierz opcję „Zapotrzebowanie”.  
7. W polu **Horyzont czasowy zapotrzebowania (dni)** wpisz „90”. W przypadku towarów w tej grupie planowanie główne utworzy sugestie uzupełnienia na maksymalnie 90 dni w przyszłość.  
8. W polu **Ilość dni** z ujemnym stanem magazynu wpisz „1”.
9. W polu **Ilość dni z dodatnim stanem magazynu** wpisz „1”.
10. Rozwiń lub zwiń sekcję **Inne**.
11. W obszarze **Marginesy bezpieczeństwa (w dniach)** w polu **Zapas czasu dla przyjęcia dodany do daty zapotrzebowania** wprowadź wartość „1”. Jeśli na przykład zapas czasu dla przyjęcia jest ustawiony na 1 dzień, a wiersz zamówienia zakupu ma zaplanowane przyjęcie w dniu 15 maja, funkcja planowania głównego wyliczy skorygowaną datę przyjęcia na 16 maja.  
12. W polu **Zapas czasu dla rozchodu odjęty od daty zapotrzebowania** wpisz „1”. Jeśli na przykład margines bezpieczeństwa jest ustawiony na 1 dzień, a wiersz zamówienia sprzedaży ma zaplanowaną dostawę w dniu 15 maja, funkcja planowania głównego wyliczy skorygowaną datę dostawy na 14 maja.  
13. W polu **Zapas czasu dla ponownego zamówienia dodany do czasu realizacji towaru** wpisz „1”.
14. Kliknij przycisk **Zapisz**.

## <a name="create-a-new-product"></a>Tworzenie nowego produktu
1. Otwórz **Okienko nawigacji > Moduły > Informacje o zarządzaniu produktem > Produkty > Wydane produkty**.
2. Kliknij przycisk **Nowy**.
3. W polu **Numer produktu** wpisz wartość.
4. W polu **Nazwa produktu** wpisz wartość.
5. W polu **Grupa modeli towaru** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
6. Na liście znajdź i zaznacz odpowiedni rekord.
7. Na liście kliknij łącze w wybranym wierszu.
8. W polu **Grupa towarów** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
9. Na liście znajdź i zaznacz odpowiedni rekord.
10. Na liście kliknij łącze w wybranym wierszu.
11. W polu **Grupa wymiarów magazynowania** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
12. Na liście znajdź i zaznacz odpowiedni rekord.
13. Na liście kliknij łącze w wybranym wierszu.
14. W polu **Grupa wymiarów śledzenia** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
15. Na liście znajdź i zaznacz odpowiedni rekord.
16. Na liście kliknij łącze w wybranym wierszu.
17. Kliknij przycisk **OK**.

## <a name="setup-default-order-settings"></a>Konfigurowanie domyślnych ustawień zamówienia
1. W **okienku akcji** kliknij pozycję **Plan**.
2. W obszarze **Ustawienia zamówień** kliknij pozycję **domyślne ustawienia zamówień**.
3. W sekcji **Zamówienie zakupu** w polu **Witryna domyślna** wpisz oddział używany jako domyślny podczas tworzenia zamówień zakupu.
4. W polu **Magazyn domyślny** wpisz oddział, w którym towar jest przechowywany.
5. Rozwiń lub zwiń sekcję **Zapasy**.
6. W polu **Wielokrotność** wpisz wartość „10”.
7. W polu **Min. ilość zamówienia** wpisz wartość „10”.
8. W polu **Maks. ilość zamówienia** wpisz wartość „100”.
9. W polu **Standardowa ilość zamówienia** wpisz wartość „10”.
10. W polu **Czas realizacji zakupu** wpisz liczbę.
11. Zaznacz lub wyczyść pole wyboru **Dni robocze**.
12. Kliknij przycisk **Zapisz**.
13. W polu **Domyślny typ zamówienia** zaznacz opcję „Zamówienie zakupu”.
14. Kliknij przycisk **Zapisz**.
15. Zamknij stronę. Zamknij stronę Ustawienia domyślne zamówień.  

## <a name="add-an-item-to-a-coverage-group"></a>Dodawanie towaru do grupy zapotrzebowania
1. Rozwiń lub zwiń sekcję **Plan**.
2. W polu **Grupa zapotrzebowania** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
3. Na liście znajdź utworzoną przez siebie **grupę zapotrzebowania**.
4. Na liście kliknij łącze w wybranym wierszu.

## <a name="create-item-coverage-rules"></a>Tworzenie reguł zapotrzebowania na towary
1. W **okienku akcji** kliknij pozycję **Plan**.
2. W obszarze **Pokrycie** kliknij opcję **pokrycie zapasu**.
3. Kliknij przycisk **Nowy**.
4. Kliknij kartę **Ogólne**.
5. Zaznacz pole wyboru w nagłówku ustawień **Zastępowanie grupy zapotrzebowania**.
6. W polu **Horyzont czasowy zapotrzebowania (dni)** wpisz „60”. Mimo iż towary w grupie zapotrzebowania Zapotrzebowanie są zaplanowane na najbliższe 90 dni, ten towar będzie zaplanowany na najbliższe 60 dni.  
7. W polu **Ilość dni** z ujemnym stanem magazynu wpisz „2”.
8. W polu **Ilość dni z dodatnim stanem magazynu** wpisz „2”.
9. Kliknij kartę **Czas realizacji**.
10. Zaznacz pole wyboru w nagłówku **Zakup**.
11. W polu **Godzina zakupu** wpisz „5”.
12. Kliknij przycisk **Zapisz**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]