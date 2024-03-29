---
title: Kopiowanie dostawców przy użyciu udostępnionych sekwencji numerów
description: W tym artykule wyjaśniono, w jaki sposób należy używać udostępnionych sekwencji numerów w celu kopiowania dostawców do innej firmy z zachowaniem niezmienionego identyfikatora dostawcy.
author: sunfzam
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 7b7285cdf454955656c4fb20c3abf68f3f9c39dc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904909"
---
# <a name="copy-vendors-by-using-shared-number-sequences"></a>Kopiowanie dostawców przy użyciu udostępnionych sekwencji numerów

[!include [banner](../includes/banner.md)]

Możesz używać udostępnionych sekwencji numerów, aby przypisywać identyfikatory dostawców. Udostępnione sekwencje numerów umożliwiają także kopiowanie dostawców z jednej firmy do innej w taki sposób, że dostawca będzie miał taki sam identyfikator w obu firmach.

## <a name="setup"></a>Konfiguracja

Aktywacja tej funkcji następuje w momencie użycia udostępnionej sekwencji numerów w celu przypisania identyfikatorów dostawców. W każdej firmie, do której chcesz skopiować dostawcę, musisz używać tej samej sekwencji numerów. Sekwencję numerów dostawców używaną w dowolnej firmie możesz zmienić na stronie **Parametry modułu rozrachunków z dostawcami**. Wybierz kolejno pozycje **Rozrachunki z dostawcami** \> **Konfiguracja** \> **Parametry modułu rozrachunków z dostawcami**, a następnie wybierz kartę **Sekwencje numerów**.

Możesz także skonfigurować sekwencje numerów dostawców dla każdej grupy dostawców. Te sekwencje numerów także muszą być udostępnione. Sekwencja numerów grupy dostawców jest używana jako pierwsza. Jeśli nie zostanie określona sekwencja numerów dla grupy dostawców, będzie używana sekwencja numerów określona na stronie **Parametry modułu rozrachunków z dostawcami**.

Możesz także kopiować dostawców między firmami, jeśli używasz ręcznie określanych identyfikatorów dostawców. Jeśli jednak spróbujesz skopiować dostawcę do firmy, w której istnieje już jego identyfikator dostawcy, proces kopiowania nie zostanie rozpoczęty.

## <a name="copy-a-vendor"></a>Kopiowanie dostawcy

Aby skopiować dostawcę, wybierz pozycję **Nowy** na stronie listy **Wszyscy dostawcy** w celu otwarcia strony **Wszyscy dostawcy, nowy rekord**. Identyfikator nowego dostawcy nie zostanie natychmiast przypisany. To działanie różni się od działania w poprzednich wersjach. Dzieje się tak dlatego, że nie wybrano jeszcze grupy dostawców, więc system nie może ustalić poprawnej sekwencji numerów do użycia. Ponadto nie może ustalić, czy próbujesz utworzyć nowego dostawcę, czy skopiować dostawcę. Dlatego też identyfikator dostawcy nie zostanie przypisany, dopóki nie wybierzesz pozycji **Zapisz** u dołu strony.

Jeśli tworzysz nowego dostawcę, możesz kontynuować wypełnianie wszystkich pól w normalny sposób. Gdy zakończysz i wybierzesz pozycję **Zapisz**, identyfikator dostawcy zostanie automatycznie przypisany. Alternatywnie, jeśli używasz określanych ręcznie sekwencji numerów, zobaczysz, że został użyty określony ręcznie identyfikator dostawcy.

Aby skopiować dostawcę, w polu **Nazwa** wprowadź co najmniej jeden znak reprezentujący dostawcę, którego szukasz. W oknie dialogowym wyszukiwania zostanie wyświetlona lista stron, które mogą reprezentować szukanego przez Ciebie dostawcę. Gdy wybierzesz jedną z tych stron, po prawej stronie okna dialogowego zostaną wyświetlone dodatkowe informacje:

- Na karcie **Ogólne** będzie widoczny numer telefonu i adres strony.
- Na karcie **Role** są widoczne role, jakie wybrana strona może mieć, oraz firmy, w których ma poszczególne role.
- Na karcie **Identyfikator podatkowy** są widoczne identyfikatory podatkowe przypisane do strony.

Stronę możesz skopiować tylko wtedy, gdy ma rolę dostawcy i gdy ma tę rolę w firmie, która nie jest bieżącą firmą. Gdy znajdziesz stronę, która spełnia te kryteria, wykonaj poniższe kroki.

1. Zostanie wyświetlona opcja **Kopiuj dostawcę**. Domyślnie ta opcja ma wartość **Nie**. Aby skopiować dostawcę do bieżącej firmy, ustaw dla tej opcji wartość **Tak**. 
2. Zostanie wyświetlone pole **Firma**. Wybierz firmę, z której ma zostać skopiowany dostawca. Jeśli dostawca istnieje tylko w jednej firmie, w tym polu domyślnie jest ustawiana ta firma.
3. Wybierz pozycję **Wybierz**. Zostanie otworzony nowy dostawca.

## <a name="validation"></a>Walidacja

Gdy kopiujesz dostawcę, system spróbuje zapisać informacje dotyczące nowego dostawcy. W celu sprawdzania, czy kopiowane dane są poprawne, są wykonywane weryfikacje. W przypadku niepowodzenia dowolnej z tych weryfikacji zostanie wyświetlony komunikat o błędzie. Komunikaty o błędach zawierają wyjaśnienia wskazujące, które informacje należy zaktualizować. Kopii dostawcy nie można zapisać do czasu poprawienia wszystkich błędów weryfikacji.

## <a name="copy-a-vendor-by-using-the-tax-exempt-number-search-feature"></a>Kopiowanie dostawcy przy użyciu funkcji wyszukiwania numeru identyfikacji podatkowej

Dostawców możesz także kopiować za pomocą funkcji wyszukiwania **Numeru identyfikacji podatkowej**, która jest dostępna w grupie **Rejestracja** na karcie **Dostawca** w okienku zadań na stronie **Wszyscy dostawcy**. W wyświetlonym oknie dialogowym **Wyszukiwanie numeru identyfikacji podatkowej** są widoczne numery identyfikacji podatkowej, identyfikator dostawcy, nazwa dostawcy oraz firma, w której jest używany dany numer identyfikacji podatkowej. Dostawcę można skopiować tylko wtedy, gdy znajduje się on w firmie, która nie jest bieżącą firmą. Po wybraniu dostawcy spełniającego to kryterium wykonaj poniższe kroki.

1. Zostanie wyświetlona opcja **Kopiuj dostawcę**. Domyślnie ta opcja ma wartość **Nie**. Aby skopiować dostawcę do bieżącej firmy, ustaw dla tej opcji wartość **Tak**.
2. Wybierz pozycję **Wybierz**. Zostanie otworzony nowy dostawca.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
