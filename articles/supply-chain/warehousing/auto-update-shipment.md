---
title: Automatyczne aktualizacje wysyłki
description: Ten temat stanowi przegląd funkcji, które umożliwiają automatyczne aktualizowanie wysyłek.
author: josaw1
manager: tfehr
ms.date: 11/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveTemplateTable,SalesTableListPage,SalesTable,WHSWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7fa2684340f5ce45b99ff9aee9937071f936b81a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435021"
---
# <a name="shipment-auto-updates"></a>Automatyczne aktualizacje wysyłki

[!include [banner](../includes/banner.md)]

Funkcja automatycznej aktualizacji wysyłki automatycznie aktualizuje ilości (zarówno zwiększenia, jak i zmniejszenia) w wierszu ładunku skojarzonym z wysyłką po zwolnieniu ładunku do magazynu. Ta funkcjonalność pozostaje włączona do momentu przetwarzania wiersza ładunku w wysyłce lub ładunku na wydaniu grupy czynności. Gdy jest używana, aktualizacje zamówienia mogą automatycznie przepływać do magazynu bez konieczności ręcznej interwencji, dopóki nie zostaną utworzone prace magazynowe.

Gdy funkcja automatycznego aktualizowania wysyłki nie jest używana, tylko ilość zmniejsza się automatycznie do momentu utworzenia pracy magazynu. Użytkownicy muszą ręcznie zaktualizować lub usunąć wiersze, a następnie muszą ponownie zwolnić wiersze, jeśli ilości zamówienia zostaną zwiększone lub zostaną dodane nowe wiersze zamówienia. Dzięki zastosowaniu funkcji automatycznej aktualizacji wysyłki firmy mogą bezproblemowo dostarczać aktualizacje do magazynu bez konieczności obawiania się, że związane z nimi wysyłki i ładunki nie odzwierciedlają aktualizacji wierszy zamówienia.

Funkcja automatycznej aktualizacji wysyłki dotyczy zarówno wierszy zamówienia sprzedaży, jak i wierszy zamówienia przeniesienia i jest włączona dla określonego magazynu. W związku z tym firmy mogą w miarę potrzeb stosować różne zasady automatycznej aktualizacji wysyłek dla magazynów. Domyślnie zasada automatycznej aktualizacji wysyłki dla zmniejszenia ilości jest stosowana dla wszystkich magazynów korzystających z procesów zarządzania magazynem. Jeśli jest używane to domyślne ustawienie zasad, tylko ilość zmniejsza się automatycznie do wysyłki i ładunku, dopóki nie zostanie utworzona praca magazynowa. To zachowanie przypomina zachowanie użyte przed wprowadzeniem funkcji automatycznej aktualizacji wysyłki.

## <a name="main-elements-of-the-functionality"></a>Główne elementy funkcjonalności

Funkcja automatycznej aktualizacji wysyłki polega przede wszystkim na statusie wysyłki w celu określenia, czy ilość w wierszu ładunku powinna zostać zmieniona, gdy zmiana jest wykonywana w wierszu zamówienia sprzedaży lub w wierszu zamówienia przeniesienia. Jest także uzależnione przede wszystkim od stanu wysyłki w celu ustalenia, kiedy nowy wiersz ładunku ma być automatycznie dodawany do istniejącego ładunku. Jeśli stan wysyłki to **W grupie czynności** lub wyższy, nie ma żadnej automatycznej aktualizacji.

Stan grupy czynności jest uwzględniany również w przypadku aktualizacji automatycznych. Jeśli dana fala związana z wierszem ładunku ma stan **Wstrzymano**, **W trakcie wykonywania**, **Zwolniono**, **Pobrano** lub **Wysłano**, jeśli użytkownik spróbuje zmniejszyć ilość w wierszu ładunku (w wyniku zmniejszenia ilości w wierszu zamówienia sprzedaży lub zamówienia przeniesienia) wyświetlany jest następujący komunikat o błędzie: „nie można usunąć rezerwacji, ponieważ utworzono pracę, która opiera się na rezerwacjach”. Ponadto, jeśli dla grupy czynności istnieje jeden z wyżej wymienionych stanów grupy czynności, jeśli użytkownik próbuje pośrednio zwiększyć ilość w wierszu ładunku przez zwiększenie ilości w wierszu zamówienia sprzedaży lub zamówienia przeniesienia, ilość w wierszu ładunku nie jest automatycznie zwiększana. W takim przypadku wiersz ładunku musi zostać ręcznie zaktualizowany.

## <a name="scenarios"></a>Scenariusze

Funkcja automatycznej aktualizacji wysyłki obsługuje cztery scenariusze: dodawanie nowego wiersza zamówienia, zwiększanie ilości w wierszu zamówienia, zmniejszanie ilości w wierszu zamówienia oraz usuwanie wiersza zamówienia.

- **Dodawanie nowego wiersza zamówienia** — gdy pole **Automatyczna aktualizacja wysyłki** na skróconej karcie **Magazyn** na stronie **Magazyny** (**Zarządzanie magazynem \> Konfiguracja \> Magazyn \> Magazyny**) mają wartość **Zawsze**, jeśli dla zamówienia istnieje wysyłka, a nowy wiersz zamówienia zostanie dodany do zamówienia sprzedaży lub zamówienia przeniesienia po utworzeniu ładunku dla zamówienia sprzedaży, istniejący ładunek nie zostanie zaktualizowany. Nowy wiersz ładunku bez odwołania do istniejącego ładunku jest tworzony i kojarzony z istniejącą wysyłką. Nowy wiersz zostanie dodany do ładunku i zwolniony.
- **Zwiększ ilość w wierszu zamówienia** - Gdy w polu **Automatyczna aktualizacja wysyłki** jest ustawiona wartość **Zawsze**, jeśli dla zamówienia istnieje wysyłka, a ilość w istniejącym wierszu zamówienia sprzedaży lub w wierszu zamówienia przeniesienia zostanie zwiększona po utworzeniu ładunku dla zamówienia sprzedaży, wiersz ładunku zwiększa się o taką samą ilość, co wiersz zamówienia. Jeśli ładunek został zwolniony, ale nie utworzono żadnej pracy, wiersz ładunku zwiększa się o taką samą ilość, co wiersz zamówienia.
- **Zmiejsz ilości w wierszu zamówienia** - Gdy w polu **Automatyczna aktualizacja wysyłki** jest ustawiona wartość **Zawsze** lub **Przy zmniejszeniu ilości**, jeśli dla zamówienia istnieje wysyłka i ilość w istniejącym wierszu zamówienia sprzedaży lub wierszu zamówienia przeniesienia zmniejszyła się po utworzeniu ładunku dla zamówienia sprzedaży, ilość w skojarzonym wierszu ładunku jest zaktualizowana, aby była zgodna,chyba że ilość w tym wierszu ładunku jest już równa lub mniejsza od nowej ilości w wierszu ładunku. W takim przypadku wiersz ładunku nie jest modyfikowany. Jeśli ładunek został zwolniony, ale nie utworzono żadnej pracy, ilość w skojarzonym wierszu ładunku jest zgodna z tym, że ilość w wierszu ładunku już jest równa lub mniejsza niż nowa ilość w wierszu zamówienia. W takim przypadku wiersz ładunku jest modyfikowany.
- **Usuwanie wiersza zamówienia** - Kiedy pole **Automatyczna aktualizacja wysyłki** ma wartość **Zawsze** lub **Przy zmniejszeniu ilości**, jeśli użytkownik spróbuje usunąć wiersz zamówienia, dla którego istnieje wiersz ładunku wyświetlany jest komunikat o błędzie.

## <a name="example-scenario"></a>Przykładowy scenariusz

W tym scenariuszu trzeba mieć zainstalowane dane demonstracyjne oraz musi być używana **USMFowa** firma danych demonstracyjnych.

### <a name="turn-on-the-auto-update-shipment-functionality"></a>Włącz funkcję automatycznej aktualizacji wysyłki

Włącz funkcję automatycznej aktualizacji wysyłki postępując zgodnie z następującymi krokami.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Magazyny**.
2. Wybierz magazyn **24**.
3. W skróconej karcie **Magazyn** w polu **Automatyczna aktualizacja wysyłki** zmień wartość z **Przy zmniejszeniu ilości** na **Zawsze**.

Po zmianie wartości na **Zawsze** wszystkie zwiększenia lub zmniejszenia ilości w wierszach zamówienia sprzedaży i zamówienia przeniesienia oraz wszelkie uzupełnienia nowych wierszy są uwzględniane w wysyłkach i ładunkach dla wybranego magazynu, uwzględniając wcześniej określone ograniczenia aktualizacji.

### <a name="change-the-wave-template-so-that-load-lines-arent-automatically-processed"></a>Umożliwia zmianę szablonu grupy czynności w taki sposób, aby wiersze ładunku nie były automatycznie przetwarzane

Aby skonfigurować szablon grupy czynności w taki sposób, aby nie przetwarzać automatycznie wierszy ładunku, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grupy czynności**.
2. Wybierz szablon grupy czynności **Domyślna 24-godzinna wysyłka**.
3. Wybierz opcję **Edycja**.
4. Na skróconej karcie **Ogólne** ustaw opcję **Automatyczne tworzenie grupy czynności** na **Tak**” i upewnij się, że wszystkie pozostałe opcje są ustawione na **Nie**.

Ważne jest, aby nie było możliwe automatyczne tworzenie i zwalnianie pracy w ramach procesu tworzenia grupy czynności Po utworzeniu pracy, która jest powiązana z wierszem ładunku utworzonym dla wiersza zamówienia sprzedaży, wiersz ładunku nie jest już automatycznie aktualizowany po zmianie ilości w wierszu zamówienia sprzedaży.

### <a name="create-a-sales-order"></a>Utwórz zamówienie sprzedaży

Aby utworzyć zamówienie sprzedaży, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
2. Wybierz odbiorcę **US-003**.
3. Utwórz wiersz dla kodu pozycji **A0001**.
4. Wpisz ilość **10**. (Upewnij się, że używasz magazynu **24**.)
5. Wybierz opcję **Zapisz**.
6. W okienku akcji na karcie **Magazyn** w grupie **Akcje** wybierz opcję **Zwolnienie do magazynu**. Zostanie utworzona wysyłka i grupa czynności.

Ponieważ w poprzedniej procedurze zmieniono szablon grupy czynności, nie jest już tworzony żaden ładunek ani praca. Stan wysyłki jest **Otwarty** i status grupy czynności jest **Utworzona**.

### <a name="decrease-the-quantity-on-a-sales-order-line"></a>Zmniejszanie ilości na wierszu zamówieniu sprzedaży

Aby zmniejszyć ilość w wierszu zamówienia sprzedaży, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
2. Wybierz zamówienie sprzedaży, które zostało właśnie wydane do magazynu.
3. Zaznacz wybrany wiersz zamówienia sprzedaży. W polu **Kwota** zmień wartość z **10** na **8**.
4. W wierszu zamówienia sprzedaży wybierz opcję **Magazyn \> Szczegóły wysyłki**. Na stronie **Szczegóły wysyłki** w skróconej karcie **Wiersze ładunku** ilość odzwierciedla zmianę w wierszu zamówienia sprzedaży.

### <a name="increase-the-quantity-on-a-sales-order-line"></a>Zwiększanie ilości na wierszu zamówieniu sprzedaży

Aby zwiększyć ilość w wierszu zamówienia sprzedaży, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
2. Wybierz zamówienie sprzedaży, które wcześniej zostało wydane do magazynu.
3. Zmień ilość w wierszu z **8** na **12**.
4. Wybierz opcję **Zapisz**.
5. Wróć do strony **Wszystkie zamówienia sprzedaży** i wybierz zamówienie sprzedaży ponownie.
5. W okienku akcji, na karcie **Magazyn**, w grupie **Informacje pokrewne** wybierz **Szczegóły wysyłki**. Na stronie **Szczegóły wysyłki** w skróconej karcie **Wiersze ładunku** ilość odzwierciedla zmianę w wierszu zamówienia sprzedaży.

Chociaż ilość w wierszu ładunku została zwiększona z 8 do 12, wówczas zarezerwowanych jest tylko osiem towarów, chyba że jest włączona automatyczna rezerwacja. Ponieważ ilość dodana do istniejącej wysyłki nie została zarezerwowana, jeśli grupa czynności jest przetwarzana w tym momencie bez rezerwacji, praca jest tworzona tylko dla ilości, która została już zarezerwowana.

> [!NOTE]
> Gdy ilość w wierszu zamówienia zostanie zmniejszona, ilość w wierszu ładunku się nie zmienia, jeśli jest już równa lub mniejsza niż nowa ilość w wierszu zamówienia. Gdy ilość w wierszu zamówienia zostanie zwiększona, wiersz ładunku zwiększa się o taką samą ilość, co wiersz zamówienia. Jeśli ilość w wierszu zamówienia różni się od ilości w wierszu ładunku, różnica pozostaje.

### <a name="add-a-sales-order-line"></a>Dodaj wiersz zamówienia sprzedaży

Aby dodać zamówienie sprzedaży, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
2. Wybierz zamówienie sprzedaży, które wcześniej zostało wydane do magazynu.
3. Utwórz wiersz dla kodu pozycji **A0002**.
4. W polu **Ilość** wpisz wartość **10**. (Upewnij się, że używasz magazynu **24**.) Nowy wiersz zostanie automatycznie dodany do istniejącej wysyłki.
5. Wybierz opcję **Zapisz**.
6. Wróć do strony **Wszystkie zamówienia sprzedaży** i wybierz zamówienie sprzedaży ponownie.
7. W okienku akcji, na karcie **Magazyn**, w grupie **Informacje pokrewne** wybierz **Szczegóły wysyłki**. Na stronie **Szczegóły wysyłki** w skróconej karcie **Wiersze ładunku** zwróć uwagę na drugi wiersz ładunku.

Ponieważ wiersz zamówienia sprzedaży dodany właśnie do istniejącej wysyłki nie został zarezerwowany, w przypadku przetwarzania grupy czynności w tym momencie praca jest tworzona tylko dla ilości w pierwszym wierszu zamówienia sprzedaży i pierwszego wiersza ładunku.

### <a name="process-a-wave"></a>Przetwarzanie grupy czynności

Aby przetworzyć grupę czynności, należy wykonać następujące czynności.

1. Przejdź do **Zarządzanie magazynem \> Wychodzące grupy czynności \> Grupy czynności wysyłki \> Wszystkie grupy czynności**.
2. Zaznacz utworzoną wcześniej grupę czynności.
3. W okienku akcji na karcie **Grupa czynności** w grupie **Grupa czynności** wybierz opcję **Przetwórz**.

Grupa czynności jest przetwarzana i tworzy pracę dla zarezerwowanych ilości w wierszach ładunku. Stan wysyłki został zaktualizowany z **Otwarty** na **W grupie czynności**. Jeśli stan wysyłki zostanie zmieniony na **W grupie czynności**, wszelkie wprowadzone zmiany, takie jak zmniejszenie lub zwiększenie ilości w wierszach lub dodanie nowych wierszy do zamówienia sprzedaży, nie mają wpływu na istniejące wiersze ładunku skojarzone z wysyłką w grupie czynności.

Jeśli wysyłka ma stan **W grupie czynności** lub wyższy, aktualizacje ilości w wierszu zamówienia sprzedaży nie są odzwierciedlane lub sprawdzane w odniesieniu do wiersza ładunku skojarzonego z wysyłką. Zmiany ilości w wierszu ładunku muszą być wprowadzane bezpośrednio w wierszu ładunku.

Sprawdzanie poprawności jest wykonywane po utworzeniu pracy dla wiersza ładunku i wykonaniu rezerwacji. Zmniejszenie ilości w wierszu zamówienia sprzedaży jest następnie sprawdzane w odniesieniu do rezerwacji wiersza pracy.
