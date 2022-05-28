---
title: Szablony punktu kontrolnego
description: W tym temacie wyjaśniono, jak skonfigurować funkcję rozliczeń za etapy w rozliczeniach subskrypcji.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: ecc4ddbb4d22eefac36f8cf8205d3b6084bd7d9d
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686499"
---
# <a name="milestone-billing"></a>Fakturowanie etapowe

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak definiować szablony dla funkcji rozliczeń etapów w rozliczeniach subskrypcji. Dla każdego wiersza w szablonie kamieni milowych można zdefiniować procent lub kwotę alokacji. Następnie można przypisać szablon kamieni milowych do elementów harmonogramu fakturowania, które korzystają z funkcji fakturowania kamieni milowych.

## <a name="add-a-template"></a>Dodaj szablon

Aby dodać szablon kamienia milowego, wykonaj następujące kroki.

1. Przejdź do **Rozliczanie subskrypcji \> Rozliczanie umowy cyklicznej \> Konfiguracja \> Szablony kamieni milowych**.
2. Wybierz pozycję **Nowy**.
3. W polu **Szablony kamieni milowych** wprowadź unikatowy identyfikator dla nowego szablonu.
4. W polu **Opis wprowadź** opis.
5. W polu **Metoda alokacji** wybierz metodę alokacji.
6. Opcjonalnie: w polu **Suma** określ łączną kwotę szablonu.
7. Wybierz pozycję **Dodaj**, aby dodać wiersz. Następnie w polu **Numer** towaru wybierz numer towaru dla nowego wiersza.
8. Wykonaj jedną z następujących czynności, zależnie od wartości wybranej w polu **Metoda alokacji**:

    - Jeśli wybrano **opcję Procent** jako metodę alokacji, w polu **Procent** określ procent alokacji dla każdego wiersza. Po określeniu wartości procentowych **suma wartości procentowych widocznych w polu Suma procent** musi być równa **100**.
    - Jeśli wybrano **Zmienna ilość** jako metodę alokacji, w polu **ilość** określ kwotę dla każdego wiersza.
    - Jeśli jako metodę alokacji wybrano opcję **Równa ilość**, nie trzeba określać kwoty. Każdy wiersz zostanie zaktualizowany odpowiednią wartością procentową i kwotą na podstawie liczby pozycji dodanych do szablonu.

9. Wybierz opcję **Zapisz**.

## <a name="delete-a-template"></a>Usuń szablon

Aby usunąć szablon kamienia milowego, wykonaj następujące kroki.

1. Wybierz co najmniej jeden wiersz do usunięcia, a następnie wybierz **Usuń**.
2. Kliknij **Tak**, jeśli zostanie wyświetlony monit o potwierdzenie wyboru.

## <a name="milestone-template-fields"></a>Pola szablonu kamienia milowego

Strona **szablonu punktu kontrolnego** zawiera następujące pola.

| Pole | Opis |
|-------|-------------| 
| Szablon punktu kontrolnego | Unikalny identyfikator szablonu kamieni milowych. |
| Opis | Opis szablonu kamieni milowych. |
| Metoda alokacji | <p>Wybierz sposób przydziału:</p><ul><li>**Procent ukończenia** — wartość skumulowanego ukończenia jest używana dla każdego wiersza.</li><li>**Procent** — dla alokacji można określić kwotę procentową. Suma wszystkich wartości procentowych musi być równa 100.</li><li>**Zmienna ilość** — Można określić kwotę alokacji. Kwota alokacji jest określana na poziomie transakcji.</li><li>**Równa kwota** — wartości procentowe alokacji są obliczane automatycznie i w równej wysokości dzielone między towary w szablonie.</li></ul> |
| Razem | Określ kwotę kamieni milowych dla szablonu. |
| **Wiersze** | |
| Numer towaru | Wybierz numer pozycji dla szablonu kamieni milowych. |
| Nazwa produktu | Nazwa towaru. |
| Wartość procentowa | <p>Umożliwia wprowadzenie procentu alokacji dla wiersza:</p><ul><li>Jeśli w polu **Metoda alokacji** jest ustawiona wartość **Procent**, należy określić wartość procentową dla wiersza.</li><li>Jeśli w **polu Metoda alokacji** jest ustawiona wartość **Równa ilość**, procent jest automatycznie dzielony na równe wartości procentowe na podstawie liczby towarów w szablonie.</li></ul><p>Suma wszystkich wartości procentowych musi być równa 100.</p><p>Jeśli w nagłówku została określona wartość **Suma**, a w wierszu zostanie zmień wartość **Procent**, zostanie zaktualizowana wartość **ilość**. I odwrotnie, jeśli zmienisz wartość **ilość**, wartość **Procent** zostanie zaktualizowana.</p> |
| Ilość | <p>Kwota alokacji dla wiersza:</p><ul><li>Jeśli w polu **Metoda alokacji** jest ustawiona wartość **Zmienna ilość**, należy określić wartość ilości dla wiersza.</li><li>Jeśli pole **Metoda alokacji** jest ustawione na **Równa ilość**, kwota jest automatycznie dzielona na równe kwoty na podstawie liczby pozycji w szablonie i wartości **Łączna ilość**, która jest określony w nagłówku.</li></ul><p>Suma wszystkich kwot musi być równa **wartości Suma** określona w nagłówku.</p><p>Jeśli w nagłówku została określona wartość **Suma**, a w wierszu zostanie zmień wartość **ilość**, zostanie zaktualizowana wartość **Procent**. I odwrotnie, jeśli zmienisz wartość **Procent**, wartość **ilość** zostanie zaktualizowana.</p> |
| **Sumy** | |
| Łączny procent | Suma wartości procentowych. Suma wszystkich wartości procentowych musi być równa 100. |
| Razem | Suma wartości **ilość** dla wszystkich wierszy. Suma wszystkich kwot musi być równa **wartości Suma** określona w nagłówku. |
| Pozostała kwota | Pozostała kwota. Wartość jest obliczana jako wartość **Łączna ilość** z nagłówka minus suma wartości **Kwota** dla wszystkich wierszy.|

## <a name="milestone-allocation"></a>Alokacja punktu kontrolnego

Przed rozpoczęciem korzystania z funkcji kamieni milowych należy wykonać te zadania.

1. Dodaj jeden lub więcej szablonów punktów kontrolnych.
2. Utwórz grupę harmonogramu rozliczeń. Określ **punkt kontrolny** jako typ elementu i wybierz szablon.
3. Na stronie **Ustawienia towaru** (**Rozliczanie subskrypcji \> Rozliczanie umowy cyklicznej \> Ustawienia \> Elementy**) wybierz relację produktu i szablon punktu kontrolnego dla konfiguracji towaru

Po utworzeniu szablonów punktów kontrolnych, grup harmonogramów fakturowania i towarów można utworzyć harmonogram fakturowania, w których jest używana ta funkcja punktów kontrolnych.

Aby skonfigurować harmonogram fakturowania, w który są używane punkty kontrolne, należy wykonać następujące kroki.

1. Na liście **Wszystkie/Aktywne harmonogramy fakturowania** na stronie **Harmonogramy** fakturowania wybierz pozycję **Nowy**.
2. Na stronie **Wszystkie harmonogramy fakturowania** utwórz nowy harmonogram fakturowania i określ konto odbiorcy oraz datę rozpoczęcia.
3. W sekcji **Harmonogram rozliczeń** wybierz pozycję **Dodaj wiersz**. Następnie dodaj numer pozycji i ustaw **pole Typ pozycji** na **Punkt kontrolny**.

    Jeśli dla towaru jest ustawiony domyślny szablon punktu kontrolnego, zdarzenia kamieni milowych są automatycznie dodawane do wierszy harmonogramu fakturowania. Daty końcowe są puste dla wierszy kamieni milowych.

    Jeśli dla tej pozycji nie jest ustawiony szablon kamieni milowych, wybierz opcję Alokacja **kamieni milowych**. Następnie na stronie **Alokacja kamieni milowych** wybierz szablon punktu kontrolnego i dokonaj wszelkich wymaganych aktualizacji. Następnie wybierz **przycisk Zamknij**, aby powrócić do harmonogramu fakturowania i zakończyć tworzenie harmonogramu fakturowania.

4. Aby utworzyć faktury dla harmonogramu fakturowania, musisz zaktualizować datę zakończenia dla każdego zdarzenia kamienia milowego. W przypadku pojedynczego harmonogramu fakturowania można zaktualizować datę zakończenia zdarzenia kamieni milowych w wierszach harmonogramu fakturowania. Aby zaktualizować wiele harmonogramów fakturowania, wybierz opcję **Aktualizuj datę ukończenia procesu**.
5. Po zaktualizowaniu daty końcowej można utworzyć fakturę. W przypadku pojedynczego harmonogramu fakturowania wybierz pozycję **Generuj fakturę** na stronie **Wszystkie harmonogramy fakturowania**. Aby utworzyć faktury dla wielu harmonogramów fakturowania, wybierz opcję **Generuj fakturę** lub **Wygeneruj przetwarzanie wsadowe faktur** w obszarze **Zadania okresowe**.

## <a name="edit-milestone-allocation-on-a-billing-schedule-line"></a>Edytuj alokację punktów kontrolnych w wierszu harmonogramu fakturowania

Aby edytować alokację kamieni milowych w wierszu harmonogramu rozliczeń, wykonaj następujące kroki.

1. Na stronie **Harmonogramy płatności** > **Wszystkie lub aktywne harmonogramy płatności** w polu **Numer harmonogramu** wybierz numer harmonogramu płatności.
2. W sekcji **Wiersze harmonogramu fakturowania** wprowadź element, **określ punkt kontrolny** jako element, a następnie wybierz alokację **kamieni milowych**.
3. W polu **Szablon punktu kontrolnego** wybierz szablon kamieni milowych.
4. Wybierz **Proces**. Wiersze szablonu kamieni milowych są automatycznie dodawane do wierszy harmonogramu fakturowania.

## <a name="milestone-allocation-fields"></a>Pola alokacji kamieni milowych

Strona **Alokacja punktu kontrolnego** zawiera następujące pola.

| Pole | Opis |
|-------|-------------|
| Pozycja nadrzędna | Numer pozycji elementu nadrzędnego. |
| Cena rozszerzona | <p>Rozszerzona cena przedmiotu. Ta wartość odpowiada wartości **kwoty netto** wiersza harmonogramu fakturowania.</p></p>W przypadku elementu nadrzędnego punktu kontrolnego domyślną wartością jest wartość **Suma** określona dla szablonu punktu kontrolnego. Jeśli łączna kwota wynosi 0 (zero), domyślną wartością jest **wartość netto** wiersza harmonogramu fakturowania.</p> |
| Szablon punktu kontrolnego | Identyfikator szablonu kamienia milowego elementu zamówienia. |
| Opis szablonu | Opis szablonu kamieni milowych. |
| Metoda alokacji | Metoda alokacji używana dla szablonu kamieni milowych. |
| **Wiersze** | Wartości domyślne dla wszystkich wierszy są oparte na wybranym szablonie kamieni milowych. Możesz je zmienić zgodnie z wymaganiami. |
| Numer towaru | Numer pozycji dla szablonu alokacji kamieni milowych. |
| Nazwa produktu | Nazwa produktu. |
| Wartość procentowa | <p>Procent alokacji dla linii. Suma wszystkich wartości procentowych musi być równa 100.</p><p>Jeśli zmienisz wartość **Procent**, wartość **Ilość netto** zostanie zaktualizowana. I odwrotnie, jeśli zmienisz wartość **Ilość netto**, wartość **Procent** zostanie zaktualizowana.</p> |
| Kwota netto | <p>Kwota alokacji dla wiersza. Suma kwot netto dla wszystkich wierszy musi być równa wartości **Cena rozszerzona** określonej w nagłówku.</p><p>Jeśli zmienisz wartość **Ilość netto**, wartość **Procent** zostanie zaktualizowana. I odwrotnie, jeśli zmienisz wartość **Procent**, wartość **Ilość netto** zostanie zaktualizowana.</p> |
| **Sumy** | |
| Łączny procent | Suma wartości **Procent** dla wszystkich wierszy. Ta suma musi być równa 100. |
| Razem | Suma wartości **Ilość netto** dla wszystkich wierszy. Suma wszystkich kwot musi być równa **Cena rozszerzona** określona w nagłówku. |
| Pozostała kwota | Pozostała kwota. Wartość jest obliczana jako wartość **Cena rozszerzona** z nagłówka minus suma wartości **Ilość netto** dla wszystkich wierszy. Ostateczna ilość musi wynosić 0 (zero). |
