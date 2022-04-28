---
title: Konfiguruj alokację przychodu wielu elementów
description: W tym temacie opisano sposób konfiguracji parametrów wielu elementów alokacji przychodów w ramach fakturowania subskrypcji.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: e422b16d1c4505b2837bb282918ecada902b806e
ms.sourcegitcommit: 23588e66e25c05e989f3212ac519d7016820430a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2022
ms.locfileid: "8566365"
---
# <a name="set-up-multiple-element-revenue-allocation"></a>Konfiguruj alokację przychodu wielu elementów

Alokacja przychodów wielu elementów umożliwia konfigurowanie różnych szablonów, które są używane do obliczania i alokowania przychodu między wieloma pozycjami. Funkcja ta może pomóc w spełnieniu wymogów kodyfikacji standardów rachunkowości Topic 606 (ASC 606) i/lub Międzynarodowego Standardu Sprawozdawczości Finansowej 15 (MSSF 15).

## <a name="multiple-element-revenue-allocation-parameters"></a>Parametry alokacji przychodu wielu elementów

Strona Parametry alokacji **przychodów z wielu elementów** zawiera parametry wielu elementów alokacji przychodów.

### <a name="standalone-selling-price-origin"></a>Źródło autonomicznej ceny sprzedaży

Pole Pochodzenie **autonomicznej ceny** sprzedaży określa źródło autonomicznej ceny sprzedaży. Tę wartość można zaktualizować na stronie **autonomicznej ceny sprzedaży towaru** oraz w transakcji. Dostępne są następujące opcje.

| Opcja | Opis |
|--------|-------------|
| Ilość | Autonomiczna cena sprzedaży to kwota, która jest większa niż 0 (zero). Kwota jest w razie potrzeby konwertowana między walutami funkcjonalnymi a walutami inicjatorami. |
| Bazowa ceny sprzedaży | Autonomiczna cena sprzedaży odpowiada podstawowej cenie sprzedaży towaru. |
| Cena faktury | Jednostkowa cena sprzedaży jest zgodna z ceną fakturową danej pozycji. |
| Procent pozycji | Autonomiczna cena sprzedaży jest określona jako wartość procentowa i jest obliczana na podstawie ceny towaru. W przypadku wybrania tej opcji należy określić domyślną wartość procentową. |
| Alokuj kwotę zaległą | <p>Pochodzenie autonomicznej ceny sprzedaży oblicza się jako *Całkowita wartość umowna pozycji nadrzędnej* - *Całkowita autonomiczna cena sprzedaży pozycji podrzędnych*:</p><ul><li>*Łączna wartość kontraktu pozycji nadrzędnej* to kwota netto lub kwota rachunku.</li><li>*Całkowita autonomiczna cena sprzedaży towarów podrzędnych* jest sumą autonomicznej ceny sprzedaży rozszerzonej lub kontraktowej wszystkich towarów podrzędnych, z wyjątkiem towaru podrzędnego, który używa tej autonomicznej ceny sprzedaży.</li></ul><p>Jeśli obliczona kwota jest wartością ujemną, jest ona ustawiana na 0 (zero).</p><p>**Uwaga:** tę opcję można wybrać tylko dla jednego towaru podrzędnego w podziale przychodów.</p> |
| Brak | Pochodzenie autonomicznej ceny sprzedaży jest oparte na pozycjach podrzędnych. Ta opcja dotyczy towarów zdefiniowanych jako towary nadrzędne w szablonie podziału przychodów. Jeśli zaznaczono pole wyboru **Podział przychodów**, ta opcja jest zaznaczona automatycznie i ustawienia nie można zmienić. |
| Procent ceny faktury nadrzędnej | Pochodzenie autonomicznej ceny sprzedaży jest procentem ceny faktury towaru nadrzędnego. Można zmienić wartość domyślną. Ta opcja jest dostępna tylko dla pozycji podrzędnych w szablonie podziału przychodów. |
| Procent nadrzędnej ceny standardowej | Źródłem autonomicznej ceny sprzedaży jest procent ceny standardowej pozycji macierzystej. Można zmienić wartość domyślną. Ta opcja jest dostępna tylko dla pozycji podrzędnych w szablonie podziału przychodów. Jest to domyślna opcja dla elementów podrzędnych. Gdy opcja dla elementu podrzędnego zostanie zmieniona z **Procent standardowej ceny elementu nadrzędnego** na **Procent ceny faktury nadrzędnej** lub z **Procent ceny faktury nadrzędnej** na **Procent standardowej ceny nadrzędnej**, obliczone wartości są również aktualizowane. |

### <a name="account-for-revenue-allocation-rounding-differences"></a>Konto do różnic zaokrąglania alokacji przychodów

Pole **Konto różnic zaokrąglania alokacji** przychodu określa konto, które jest używane do rekordów wszelkich korekt zaokrąglania kwoty przychodu z umowy. Jest on dostępny w przypadku korzystania z fakturowania umowy cyklicznej.

## <a name="item-standalone-selling-price"></a>Autonomiczna cena sprzedaży pozycji

Strona Autonomiczna **cena sprzedaży towaru** umożliwia określenie pochodzenia i autonomicznej ceny sprzedaży towaru. Wartości określone na tej stronie są używane jako wartości domyślne na stronie **Alokacja przychodów** w wielu elementach alokacji przychodów i cyklicznych fakturowania umów.

### <a name="specify-item-standalone-selling-price"></a>Określ autonomiczną cenę sprzedaży pozycji

Aby określić autonomiczną cenę towaru, należy wykonać następujące kroki.

1. Na stronie **Autonomiczna cena sprzedaży towaru** w polu **Pochodzenie autonomicznej** ceny sprzedaży wybierz pochodzenie autonomicznej ceny sprzedaży.
2. Wykonaj jedną z następujących czynności, zależnie od wartości wybranej w polu **Pochodzenie jednostkowej ceny sprzedaży**:

    * Jeśli wybrano **opcję Procent towaru**, określ wartość procentową w polu **Procent**.
    * Jeśli wybrano opcję **Kwota**, określ kwotę w polu **Autonomiczna cena sprzedaży**.

2. Dla każdego elementu, który ma zostać dodany do listy, wybierz **Dodaj**.
3. W polu **Kod pozycji** wybierz kod towaru. W polu **Relacja produktu** wybierz numer relacji. W przypadku pozycji, dla których pole wyboru **Podział przychodów** jest zaznaczone, wybrana kombinacja kodu pozycji i relacji między pozycjami musi być unikalna.
4. Zmień zgodnie z wymagającą wartością **domyślną pola Autonomiczne źródło ceny sprzedaży**, **Autonomiczna cena sprzedaży** lub **Procent**.
5. Dla każdego elementu nadrzędnego, który ma zostać dodany do listy, wybierz **Dodaj**.
6. W polu **Kod pozycji** wybierz kod towaru. W polu **Relacja produktu** wybierz numer relacji.
7. Zaznacz pole wyboru **Podział przychodów**.
8. W polu **Relacja produktu** wybierz numer relacji. Lista zostanie zaktualizowana przy użyciu elementu nadrzędnego i wszystkich elementów podrzędnych.
9. W przypadku towaru podrzędnego zmień domyślną wartość w polach **Autonomiczne źródło ceny sprzedaży**, **Procent nadrzędnej ceny standardowej**, **Procent nadrzędnej ceny faktury** lub **Zaalokuj pozostałą kwotę zgodnie z wymaganymi wartościami**.
10. Aby dodać kilka towarów jednocześnie, wybierz opcję **Dodaj towary**.
11. Zaktualizuj zapytanie, aby wybrać zakres elementów, które chcesz dodać.
12. Wybierz **przycisk OK**, przejrzyj listę dodanych elementów i wybierz przycisk **OK**.

### <a name="fields"></a>Pola

Strona **autonomicznej ceny sprzedaży pozycji** zawiera następujące pola.

| Pole | Opis |
|-------|-------------|
| Źródło autonomicznej ceny sprzedaży | <p>Umożliwia wybór źródła autonomicznej ceny sprzedaży:</p><ul><li>**Kwota** – Autonomiczna cena sprzedaży to kwota, która jest większa niż 0 (zero). Kwota jest w razie potrzeby konwertowana między walutami funkcjonalnymi a walutami inicjatorami.</li><li>**Podstawowa cena sprzedaży** – Autonomiczna cena sprzedaży odpowiada podstawowej cenie sprzedaży towaru.</li><li>**Cena na fakturze** – Jednostkowa cena sprzedaży jest zgodna z ceną fakturową danej pozycji.</li><li>**Odsetek pozycji** – Autonomiczna cena sprzedaży jest określona jako wartość procentowa i jest obliczana na podstawie ceny towaru. W przypadku wybrania tej opcji należy określić domyślną wartość procentową.</li></ul>**Zaalokuj pozostałą kwotę zgodnie z wymaganymi wartościami** – Pochodzenie autonomicznej ceny sprzedaży oblicza się jako *Całkowita wartość umowna pozycji nadrzędnej* - *Całkowita autonomiczna cena sprzedaży pozycji podrzędnych*:</p><ul><li>*Łączna wartość kontraktu pozycji nadrzędnej* to kwota netto lub kwota rachunku.</li><li>*Całkowita autonomiczna cena sprzedaży towarów podrzędnych* jest sumą autonomicznej ceny sprzedaży rozszerzonej lub kontraktowej wszystkich towarów podrzędnych, z wyjątkiem towaru podrzędnego, który używa tej autonomicznej ceny sprzedaży.</li></ul><p>Jeśli obliczona kwota jest wartością ujemną, jest ona ustawiana na 0 (zero).</p><p>**Uwaga:** tę opcję można wybrać tylko dla jednego towaru podrzędnego w podziale przychodów.</p></li><li>**Brak** – Pochodzenie autonomicznej ceny sprzedaży jest oparte na pozycjach podrzędnych. Ta opcja dotyczy towarów zdefiniowanych jako towary nadrzędne w szablonie podziału przychodów. Jeśli zaznaczono pole wyboru **Podział przychodów**, ta opcja jest zaznaczona automatycznie i ustawienia nie można zmienić.</li><li>**Procent nadrzędnej ceny faktury** – Pochodzenie autonomicznej ceny sprzedaży jest procentem ceny faktury towaru nadrzędnego. Można zmienić wartość domyślną. Ta opcja jest dostępna tylko dla pozycji podrzędnych w szablonie podziału przychodów.</li><li>**Procent standardowej ceny rodzica** – Źródłem autonomicznej ceny sprzedaży jest procent ceny standardowej pozycji macierzystej. Można zmienić wartość domyślną. Ta opcja jest dostępna tylko dla pozycji podrzędnych w szablonie podziału przychodów. Jest to domyślna opcja dla elementów podrzędnych. Gdy opcja dla elementu podrzędnego zostanie zmieniona z **Procent standardowej ceny elementu nadrzędnego** na **Procent ceny faktury nadrzędnej** lub z **Procent ceny faktury nadrzędnej** na **Procent standardowej ceny nadrzędnej**, obliczone wartości są również aktualizowane.</li></ul> |
| Autonomiczna cena sprzedaży | Określ samodzielną cenę sprzedaży artykułu. To pole jest dostępne, gdy w polu **Pochodzenie autonomicznej ceny** sprzedaży jest ustawiona wartość **Kwota**. |
| Procent | Określ procentową wartość jednostkowej ceny sprzedaży. To pole jest dostępne, gdy **w polu Pochodzenie autonomicznej** ceny sprzedaży jest ustawiona wartość **Procent towaru**, **Procent nadrzędnej ceny faktury** lub **Procent nadrzędnej ceny standardowej**. |
| Podział przychodu | <p>Umożliwia określenie, czy w wierszu jest używany podział przychodów:</p><ul><li>**Zaznaczone** — w polu Relacja towaru można **wybrać tylko towary, dla których jest ustawiony szablon** podziału przychodu. To pole wyboru można zaznaczyć tylko dla pozycji nadrzędnych szablonu podziału przychodów.</li><li>**Wyczyszczono** — towar jest towarem standardowym, który nie używa podziału przychodu.</li></ul> |
| Relacja | Symbol wskazuje, czy towar jest nadrzędny czy podrzędny w podziale przychodów. |
| Kod pozycji | <p>Wybierz kod towaru: **Tabela** albo **Grupa**.</p><p>Jeśli zaznaczone jest pole wyboru **Podział przychodów**, pole to jest ustawione na **Tabela**, a jego wartości nie można zmienić.</p> |
| Relacja produktu | <p>Wybierz numer pozycji.</p><p>Jeśli zaznaczono pole wyboru **Podział przychodów**, do wyboru będą dostępne tylko pozycje, które są pozycjami nadrzędnymi, dla których ustawiono szablon podziału przychodów. Po wybraniu elementu nadrzędnego lista jest automatycznie aktualizowana o elementy podrzędne tego elementu nadrzędnego.</p> |
| Pozycja nadrzędna | W przypadku towaru nadrzędnego w tym polu jest przedstawiany numer towaru. W przypadku towarów podrzędnych w podziale przychodu jest przedstawiany numer towaru nadrzędnego. |

## <a name="mea-templates"></a>Szablony MEA

Strona Szablony **MEA umożliwia** tworzenie i edytowanie wielu identyfikatorów szablonów układów elementów (MEA). Te identyfikatory są używane na stronie **Alokacja przychodu** do grupowania towarów.

### <a name="create-a-template"></a>Utwórz szablon

Aby skonfigurować szablon MEA, należy wykonać następujące czynności.

1. Na stronie **Szablony MEA** wybierz opcję **Nowe**.
1. W polu **Identyfikator szablonu MEA** wprowadź unikatowy identyfikator.
1. W polu **Opis wprowadź** opis.
1. W polu **Konto przychodu odroczonego** kontraktu wybierz konto, które ma być służące do wpisów w arkuszu podczas tworzenia faktury umowy MEA. To pole jest dostępne, gdy jest włączona i używana funkcja cyklicznego fakturowania umowy.
1. Wybierz opcję **Zapisz**.
