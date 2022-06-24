---
title: Reguła zwolnienia do magazynu
description: Ten artykuł zawiera informacje dotyczące funkcji reguł Zwolnienia do magazynu, która zapewnia elastyczność podczas zwalniania do magazynu. Dodaje opcję konfiguracji, która określa, czy system zezwala na zwalnianie częściowo zarezerwowanych wierszy zamówienia.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: c011938438be32e8a3169d90561ab329da32e32a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895475"
---
# <a name="release-to-warehouse-rule"></a>Reguła zwolnienia do magazynu

[!include [banner](../includes/banner.md)]

Funkcja *Reguły zwalniania do magazynu* zapewnia elastyczność podczas zwalniania do magazynu. Dodaje opcję konfiguracji dla każdego magazynu. Ta opcja służy do określania, czy dla danego magazynu można zwalniać częściowo zarezerwowane wiersze zamówienia. Funkcja ta działa z zaawansowanymi funkcjami przeładunku kompletacyjnego w sytuacjach, w których część ilości w wierszu zamówienia jest oznaczona jako źródło dostaw, ale pozostała część może zostać przetworzona w magazynie. Z tego powodu wiersz można zwolnić, aby można było kontynuować przetwarzanie dostępnej ilości zapasów.

## <a name="turn-on-and-initialize-the-release-to-warehouse-rule-feature"></a>Włącz i zainicjuj funkcję Reguły zwalniania do magazynu

### <a name="turn-on-the-feature"></a>Włączanie funkcji

Aby móc używać funkcji *Reguła zwalniania do magazynu*, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Reguła zwalniania do magazynu*

### <a name="initialize-the-feature"></a>Inicjowanie funkcji

Po włączeniu funkcji w systemie należy ją zainicjować, aby skonfigurować regułę do prawidłowego stanu początkowego dla wszystkich magazynów.

- W przypadku magazynów, w których nie włączono zarządzania magazynem, reguła jest początkowo ustawiona jako **Niestosowana**.
- W przypadku magazynów, w których włączono zarządzanie magazynem, reguła jest początkowo ustawiona jako **Zezwalaj na częściową rezerwację**

Aby zainicjować funkcję i ustawić dla niej regułę zwalniania dla wszystkich magazynów, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Parametry zarządzania magazynem**.
1. Na stronie **Parametry zarządzania magazynem** na karcie **Ogólne**, w sekcji **Informacje o firmie** wybierz łącze dla reguły **Inicjowania zwolnienia do magazynu**. (Jeśli łącze nie jest widoczne, funkcja nie jest włączona lub została już zainicjowana.)
1. Po wyświetleniu monitu o potwierdzenie akcji wybierz **Tak**, aby zainicjować tę funkcję.

## <a name="set-the-release-to-warehouse-rule-for-each-warehouse"></a><a name="set-option-warehouse"></a>Ustawienie reguły zwolnienia do magazynu dla każdego magazynu

Po włączeniu i zainicjowaniu funkcji wszystkie magazyny będą korzystać z ustawień początkowych, zgodnie z opisem w poprzedniej sekcji. To ustawienie można zmienić dla poszczególnych magazynów, wykonując następujące kroki:

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Magazyny**.
1. Wybierz magazyn do skonfigurowania.
1. Wybierz opcję **Edytuj**, aby umieścić stronę w trybie edycji.
1. Na skróconej karcie **Magazyn** w sekcji **Rezerwacje** pole **Konieczność rezerwowania zapasów** kontroluje, czy dozwolone jest częściowe zwalnianie zamówień. Należy wybrać jedną z następujących opcji:

    - **Nie dotyczy** – gdy ta funkcja jest po raz pierwszy włączona i zainicjowana, ta wartość jest automatycznie przypisana do wszystkich magazynów, w których nie włączono funkcji zarządzania magazynem. Nie można zmienić tej wartości. Ta wartość nie jest dostępna dla magazynów, w których włączona jest funkcja zarządzania magazynem.
    - **Zezwalaj na rezerwację częściową** – zamówienia mogą być zwalniane, gdy dowolna ilość jest zarezerwowana. System oceni, czy niezarezerwowana ilość powinna być oznaczona do zaawansowania przeładunku komplementarnego i oznaczyć tę ilość jako wymaganą. Jeśli nie istnieje żadne oznaczenie, system utworzy pracę tylko dla zarezerwowanej ilości. Gdy ta funkcja jest po raz pierwszy włączona i zainicjowana, ta wartość jest automatycznie przypisana do wszystkich magazynów, w których włączono funkcję zarządzania magazynem. Ta wartość nie jest dostępna dla magazynów, w których wyłączona jest funkcja zarządzania magazynem.
    - **Wymagaj pełnej rezerwacji** – zamówienia mogą być zwalniane tylko wtedy, gdy cała ilość jest zarezerwowana. Nie można ich zwolnić, jeśli całkowita ilość nie jest fizycznie zarezerwowana ani planowana dla przeładunku komplementarnego. Ta wartość nie jest dostępna dla magazynów, w których wyłączona jest funkcja zarządzania magazynem.

1. Wybierz opcję **Zapisz**.

## <a name="scenarios"></a>Scenariusze

Ta sekcja zawiera dwa scenariusze, w których można się dowiedzieć, jak działa funkcja i jak jej używać.

### <a name="make-sample-data-available"></a>Udostępnianie danych pokazowych

Aby pracować z tymi scenariuszami przy użyciu określonych przykładowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe [dane demonstracyjne](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md). Dodatkowo należy również wybrać firmę **USMF** przed rozpoczęciem.

Tych scenariuszy można również używać jako wskazówek dotyczących danej funkcji podczas pracy w produkcji. Jednak w takim przypadku trzeba podstawiać własne wartości i w niektórych przypadkach może brakować pewnych typów wymaganych rekordów, które są dostępne w standardowych danych demonstracyjnych.

### <a name="scenario-1-require-full-release-no-planned-cross-docking"></a><a name="scenario1"></a>Scenariusz 1: Wymagaj pełnego zwolnienia (bez planowanego przeładunku kompletacyjnego)

W tym scenariuszu przedstawiono sposób działania funkcji dla magazynów, dla których ustawiono **Wymaganie pełnej rezerwacji**.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Magazyny**.
1. W przypadku magazynu _62_ należy określić wymaganie, aby pole **Rezerwacja zapasów** wymagało **Pełnej rezerwacji**, jak to opisano w [regułach zwalniania do magazynu dla każdej sekcji magazynowej](#set-option-warehouse), wcześniej w tym artykule.
1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Wybierz pozycję **Nowe**, aby utworzyć nowe zamówienie sprzedaży.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:

    - Na skróconej karcie **Odbiorca**, w polu **Konto odbiorcy**, należy ustawić wartość _US-004_.
    - Na skróconej karcie **Ogólne** w polu **Magazyn** ustaw wartość _62_.

1. Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i utworzyć nowe zamówienie zakupu.
1. Nowe zamówienie zakupu (PO) zostało otwarte. Zawiera pusty wiersz w siatce w sekcji **Wiersze zamówienia sprzedaży**. W nowym wierszu ustaw następujące wartości:

    - **Numer pozycji:** *A0001*
    - **Ilość:** *2*

1. Wybierz polecenie **Dodaj wiersz**, aby dodać nowy wiersz i określ następujące wartości:

    - **Numer pozycji:** *A0002*
    - **Ilość:** *2*

1. Zaznacz pierwszy wiersz zamówienia, a następnie w menu **Zapasy** nad siatką wybierz opcję **Rezerwacja**.
1. Na stronie **Rezerwacja** wybierz opcję **Rezerwacja partii**, aby zarezerwować pełną ilość z wybranego wiersza w magazynie.
1. Zamknij stronę **Rezerwacja**, aby powrócić do zamówienia sprzedaży.
1. Nie rezerwuj drugiego wiersza zamówienia.
1. W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.
1. Zauważ, że jest wyświetlany następujący komunikat o błędzie: Pełna ilość musi być fizycznie zarezerwowana”. Z tego powodu system nie tworzy żadnej pracy, wysyłki ani ładunku dla zamówienia.

    > [!NOTE]
    > Ten sam komunikat o błędzie zostanie wyświetlony, jeśli zostanie częściowo zarezerwowany drugi wiersz.

### <a name="scenario-2-allow-partial-release"></a>Scenariusz 2: Zezwalaj na zwalnianie częściowe

W tym scenariuszu przedstawiono sposób działania funkcji dla magazynów, dla których ustawiono **Zezwolenie częściowe**.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Magazyny**.
1. W przypadku magazynu _62_ należy określić wymaganie, aby pole **Rezerwacja zapasów** zezwalało na **Częściowe zwolnienie**, jak to opisano w [regułach zwalniania do magazynu dla każdej sekcji magazynowej](#set-option-warehouse), wcześniej w tym artykule.
1. Podobnie jak w [poprzednim scenariuszu](#scenario1), należy przejść do **Zamówień sprzedaży i marketingu \> Zamówień sprzedaży \> Wszystkich zamówień sprzedaży** i utworzyć zamówienie sprzedaży dla konta odbiorcy _US-004_ z magazynu _62_. Dodaj następujące dwa wiersze zamówienia:

    - **Wiersz 1:** Ustaw pole **Kod towaru** na _A0001_, natomiast pole **Ilość** ustaw na _2_, a pole **Jednostka** na _Pcs_.
    - **Wiersz 2:** Ustaw pole **Kod towaru** na _A0002_, natomiast pole **Ilość** ustaw na _2_, a pole **Jednostka** na _Pcs_.

1. Podobnie jak w [poprzednim scenariuszu](#scenario1), należy zarezerwować pełną ilość dla wiersza zamówienia 1, ale nie rezerwować wiersza zamówienia 2.
1. W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.
1. Zwróć uwagę, że tym razem nie jest wyświetlany komunikat o błędzie. Zamiast tego system tworzy pracę, wysyłki i ładunki zależnie od potrzeby i pokazuje wyniki.
1. Aby wyświetlić informacje dotyczące wysyłki, ładunku i pracy, należy skorzystać z opcji dostępnych w menu **Magazyn** powyżej siatki:

    - **Wiersz 1:** Dostępne są trzy opcje: **Szczegóły dotyczące wysyłki**, **Szczegóły ładunku** i **Szczegóły pracy**. Zaznacz każdą opcję, aby wyświetlić szczegóły wysyłki, ładunku i pracy, które zostały utworzone podczas zwalniania zamówienia do magazynu.
    - **Wiersz 2:** Tylko opcja **Szczegóły pracy** jest dostępna. Należy ją zaznaczyć. Zauważ, że nie utworzono żadnej pracy, ponieważ nie zarezerwowano zapasów. Z tego powodu nie utworzono żadnej wysyłki ani ładunku.

> [!NOTE]
> Ten sam wynik jest oczekiwany, gdy drugi wiersz jest częściowo zarezerwowany. W takim przypadku praca zostanie utworzona dla zarezerwowanej ilości w wierszu, ale nie dla ilości niezarezerwowanej.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]