---
title: Definiowanie reguł zapotrzebowania na towary
description: Procedura przedstawia sposób tworzenia reguł zapotrzebowania i zastępowania ustawień zapotrzebowania dla określonego towaru. Pokazuje także sposób określania domyślnych ustawień zapasów.
author: t-benebo
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqGroup, DefaultDashboard, EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bca0e1786adb08a7cd4795b49c974ab95183b1dd
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469330"
---
# <a name="define-coverage-rules-for-items"></a>Definiowanie reguł zapotrzebowania na towary

[!include [banner](../../includes/banner.md)]

Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Procedura przedstawia sposób tworzenia reguł zapotrzebowania i zastępowania ustawień zapotrzebowania dla określonego towaru. Pokazuje także sposób określania domyślnych ustawień zapasów.

## <a name="create-a-coverage-group"></a>Tworzenie grupy zapotrzebowania

Utwórz grupę zapotrzebowania, wykonując następujące czynności:

1. Przejdź do **okienka nawigacji > Moduły > Planowanie główne > Ustawienia > Grupy zapotrzebowania**.
1. Wybierz pozycję **Nowy**.
1. W polu **Grupa zapotrzebowania** wpisz wartość.
1. W polu **Nazwa** wpisz wartość.
1. W polu **Kalendarz** wpisz wartość. Wybierz kalendarz, którego funkcja planowania głównego będzie używać do tworzenia sugestii uzupełniania towarów z tej grupy.  
1. W polu **Kod zapotrzebowania** wybierz opcję. W tej procedurze wybierz opcję „Zapotrzebowanie”.  
1. W polu **Horyzont czasowy zapotrzebowania (dni)** wpisz „90”. W przypadku towarów w tej grupie planowanie główne utworzy sugestie uzupełnienia na maksymalnie 90 dni w przyszłość.  
1. W polu **Ilość dni** z ujemnym stanem magazynu wpisz „1”.
1. W polu **Ilość dni z dodatnim stanem magazynu** wpisz „1”.
1. Rozwiń lub zwiń sekcję **Inne**.
1. W obszarze **Marginesy bezpieczeństwa (w dniach)** w polu **Zapas czasu dla przyjęcia dodany do daty zapotrzebowania** wprowadź wartość „1”. Jeśli na przykład zapas czasu dla przyjęcia jest ustawiony na 1 dzień, a wiersz zamówienia zakupu ma zaplanowane przyjęcie w dniu 15 maja, funkcja planowania głównego wyliczy skorygowaną datę przyjęcia na 16 maja.
1. W polu **Zapas czasu dla rozchodu odjęty od daty zapotrzebowania** wpisz „1”. Jeśli na przykład margines bezpieczeństwa jest ustawiony na 1 dzień, a wiersz zamówienia sprzedaży ma zaplanowaną dostawę w dniu 15 maja, funkcja planowania głównego wyliczy skorygowaną datę dostawy na 14 maja.  
1. W polu **Zapas czasu dla ponownego zamówienia dodany do czasu realizacji towaru** wpisz „1”.
1. Wybierz opcję **Zapisz**.

## <a name="create-a-new-product"></a>Tworzenie nowego produktu

Utwórz nowy produkt, wykonując następujące czynności:

1. Otwórz **Okienko nawigacji > Moduły > Informacje o zarządzaniu produktem > Produkty > Wydane produkty**.
1. Wybierz pozycję **Nowy**.
1. W polu **Numer produktu** wpisz wartość.
1. W polu **Nazwa produktu** wpisz wartość.
1. W polu **Grupa modeli towaru** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
1. Na liście znajdź i zaznacz odpowiedni rekord.
1. Na liście wybierz łącze w wybranym wierszu.
1. W polu **Grupa towaru** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
1. Na liście znajdź i zaznacz odpowiedni rekord.
1. Na liście wybierz łącze w wybranym wierszu.
1. W polu **Grupa wymiarów magazynowania** wybierz przycisk rozwijany, aby otworzyć wyszukiwanie.
1. Na liście znajdź i zaznacz odpowiedni rekord.
1. Na liście wybierz łącze w wybranym wierszu.
1. W polu **Grupa wymiarów śledzenia** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
1. Na liście znajdź i zaznacz odpowiedni rekord.
1. Na liście wybierz łącze w wybranym wierszu.
1. Kliknij przycisk **OK**.

## <a name="set-up-default-order-settings"></a>Konfigurowanie domyślnych ustawień zamówienia

Aby skonfigurować domyślne ustawienia zamówienia, należy:

1. W okienku **akcji** wybierz opcję **Plan**.
1. W obszarze **Ustawienia zamówień** wybierz pozycję **domyślne ustawienia zamówień**.
1. W sekcji **Zamówienie zakupu** w polu **Witryna domyślna** wpisz oddział używany jako domyślny podczas tworzenia zamówień zakupu.
1. W polu **Magazyn domyślny** wpisz oddział, w którym towar jest przechowywany.
1. Rozwiń lub zwiń sekcję **Zapasy**.
1. W polu **Wielokrotność** wpisz wartość „10”.
1. W polu **Min. ilość zamówienia** wpisz wartość „10”.
1. W polu **Maks. ilość zamówienia** wpisz wartość „100”.
1. W polu **Standardowa ilość zamówienia** wpisz wartość „10”.
1. W polu **Czas realizacji zakupu** wpisz liczbę.
1. Zaznacz lub wyczyść pole wyboru **Dni robocze**.
1. Wybierz opcję **Zapisz**.
1. W polu **Domyślny typ zamówienia** zaznacz opcję „Zamówienie zakupu”.
1. Wybierz opcję **Zapisz**.
1. Zamknij stronę. Zamknij stronę Ustawienia domyślne zamówień.  

## <a name="add-an-item-to-a-coverage-group"></a>Dodawanie towaru do grupy zapotrzebowania

Dodaj towar do grupy zapotrzebowania, wykonując następujące czynności:

1. Rozwiń lub zwiń sekcję **Plan**.
1. W polu **Grupa zapotrzebowania** wybierz przycisk rozwijany, aby otworzyć wyszukiwanie.
1. Na liście znajdź utworzoną przez siebie **grupę zapotrzebowania**.
1. Na liście wybierz łącze w wybranym wierszu.

## <a name="create-item-coverage-rules"></a>Tworzenie reguł zapotrzebowania na towary

Utwórz reguły pokrycia towaru, wykonując następujące czynności:

1. W okienku **akcji** wybierz opcję **Plan**.
1. W obszarze **Pokrycie** wybierz opcję **pokrycie zapasu**.
1. Wybierz pozycję **Nowy**.
1. Kliknij kartę **Ogólne**.
1. Zaznacz pole wyboru w nagłówku ustawień **Zastępowanie grupy zapotrzebowania**.
1. W polu **Horyzont czasowy zapotrzebowania (dni)** wpisz „60”. Mimo iż towary w grupie zapotrzebowania Zapotrzebowanie są zaplanowane na najbliższe 90 dni, ten towar będzie zaplanowany na najbliższe 60 dni.  
1. W polu **Ilość dni** z ujemnym stanem magazynu wpisz „2”.
1. W polu **Ilość dni z dodatnim stanem magazynu** wpisz „2”.
1. Wybierz kartę **Czas realizacji**.
1. Zaznacz pole wyboru w nagłówku **Zakup**.
1. W polu **Godzina zakupu** wpisz „5”.
1. Wybierz opcję **Zapisz**.

> [!NOTE]
> W przypadku towarów wytwarzanych **Terminy realizacji produkcji** są stosowane w przypadku, gdy dla towaru nie istnieje marszruta. Jeśli z towarem skojarzono aktywną marszrutę, planowanie główne zaplanuje zamówienie i oblicza jego daty zgodnie z czasem marszruty i zdolnościami produkcyjnymi zasobów (jeśli są dostępne).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
