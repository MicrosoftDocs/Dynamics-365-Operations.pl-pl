---
title: "Kopiowanie odbiorców przy użyciu udostępnionych sekwencji numerów"
description: "W tym temacie wyjaśniono, w jaki sposób należy używać udostępnionych sekwencji numerów w celu kopiowania odbiorców do innej firmy z zachowaniem niezmienionego identyfikatora odbiorcy."
author: mikefalkner
manager: aolson
ms.date: 08/31/2018
ms.topic: index-page
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.1
ms.translationtype: HT
ms.sourcegitcommit: c5d4fb53939d88fcb1bd83d70bc361ed9879f298
ms.openlocfilehash: 08e939f87bc4a1769533b205bc5706648e1d1dce
ms.contentlocale: pl-pl
ms.lasthandoff: 10/01/2018

---

# <a name="copy-customers-by-using-shared-number-sequences"></a>Kopiowanie odbiorców przy użyciu udostępnionych sekwencji numerów

[!include [banner](../includes/banner.md)]

Możesz używać udostępnionych sekwencji numerów, aby przypisywać identyfikatory odbiorców. Udostępnione sekwencje numerów umożliwiają także kopiowanie odbiorców z jednej firmy do innej w taki sposób, że odbiorca będzie miał taki sam identyfikator w obu firmach.

## <a name="setup"></a>Konfiguracja

Aktywacja tej funkcji następuje w momencie użycia udostępnionej sekwencji numerów w celu przypisania identyfikatorów odbiorców. W każdej firmie, do której chcesz skopiować odbiorcę, musisz używać tej samej sekwencji numerów. Sekwencję numerów odbiorców używaną w dowolnej firmie możesz zmienić na stronie **Parametry modułu rozrachunków z odbiorcami**. Wybierz kolejno pozycje **Rozrachunki z odbiorcami** \> **Parametry**, a następnie wybierz kartę **Sekwencje numerów**.

Możesz także skonfigurować sekwencje numerów odbiorców dla każdej grupy odbiorców. Te sekwencje numerów także muszą być udostępnione. Sekwencja numerów grupy odbiorców jest używana jako pierwsza. Jeśli nie zostanie określona sekwencja numerów dla grupy odbiorców, będzie używana sekwencja numerów określona na stronie **Parametry modułu rozrachunków z odbiorcami**.

Możesz także kopiować odbiorców między firmami, jeśli używasz ręcznie określanych identyfikatorów odbiorców. Jeśli jednak spróbujesz skopiować odbiorcę do firmy, w której istnieje już jego identyfikator, proces kopiowania nie zostanie rozpoczęty.

## <a name="copy-a-customer"></a>Kopiowanie odbiorcy

Aby skopiować odbiorcę, wybierz pozycję **Nowy** na stronie listy **Wszyscy odbiorcy** w celu otwarcia okna dialogowego **Utwórz odbiorcę**. Zauważ, że identyfikator nowego odbiorcy nie zostanie przypisany natychmiast. To zachowanie różni się od zachowania w poprzednich wersjach rozwiązania Microsoft Dynamics 365 for Finance and Operations. Dzieje się tak dlatego, że nie wybrano jeszcze grupy odbiorców, więc system nie może ustalić poprawnej sekwencji numerów do użycia. Ponadto nie może ustalić, czy próbujesz utworzyć nowego odbiorcę, czy skopiować odbiorcę. Dlatego też identyfikator odbiorcy nie zostanie przypisany, dopóki nie wybierzesz pozycji **Zapisz** u dołu okna dialogowego.

Jeśli tworzysz nowego odbiorcę, możesz kontynuować wypełnianie wszystkich pól w normalny sposób. Gdy skończysz i wybierzesz pozycję **Zapisz**, zobaczysz, że identyfikator odbiorcy został przypisany automatycznie. Alternatywnie, jeśli używasz określanych ręcznie sekwencji numerów, zobaczysz, że został użyty określony ręcznie identyfikator odbiorcy.

Aby skopiować odbiorcę, w polu **Nazwa** wprowadź co najmniej jeden znak reprezentujący odbiorcę, którego szukasz. W oknie dialogowym wyszukiwania zostanie wyświetlona lista stron, które mogą reprezentować szukanego przez Ciebie odbiorcę. Gdy wybierzesz jedną z tych stron, po prawej stronie okna dialogowego zostaną wyświetlone dodatkowe informacje:

- Na karcie **Ogólne** będzie widoczny numer telefonu i adres strony.
- Na karcie **Role** są widoczne role, jakie wybrana strona może mieć, oraz firmy, w których ma poszczególne role.
- Na karcie **Identyfikator podatkowy** są widoczne identyfikatory podatkowe przypisane do strony.

Stronę możesz skopiować tylko wtedy, gdy ma rolę odbiorcy i gdy ma tę rolę w firmie, która nie jest bieżącą firmą. Gdy znajdziesz stronę, która spełnia te kryteria, wykonaj poniższe kroki.

1. Zostanie wyświetlona opcja **Kopiuj odbiorcę**. Domyślnie ta opcja ma wartość **Nie**. Aby skopiować odbiorcę do bieżącej firmy, ustaw dla tej opcji wartość **Tak**. 
2. Zostanie wyświetlone pole **Firma**. Wybierz firmę, z której ma zostać skopiowany odbiorca. Jeśli odbiorca istnieje tylko w jednej firmie, w tym polu domyślnie jest ustawiana ta firma.
3. Wybierz pozycję **Wybierz**. Zostanie otworzony nowy odbiorca.

## <a name="validation"></a>Weryfikacja

Gdy kopiujesz odbiorcę, system próbuje zapisać informacje dotyczące nowego odbiorcy. W celu sprawdzania, czy kopiowane informacje są poprawne, są wykonywane weryfikacje. W przypadku niepowodzenia dowolnej z tych weryfikacji zostanie wyświetlony komunikat o błędzie. Komunikaty o błędach zawierają wyjaśnienia wskazujące, które informacje należy zaktualizować. Kopii odbiorcy nie można zapisać do czasu poprawienia wszystkich błędów weryfikacji.

## <a name="copy-a-customer-by-using-tax-exempt-number-search-feature"></a>Kopiowanie odbiorcy przy użyciu funkcji wyszukiwania numeru identyfikacji podatkowej

Odbiorców możesz także kopiować za pomocą funkcji wyszukiwania numeru identyfikacji podatkowej, która jest dostępna w grupie **Rejestracja** na karcie **Odbiorca** w okienku akcji na stronie **Wszyscy odbiorcy**. W wyświetlonym oknie dialogowym **Wyszukiwanie numeru identyfikacji podatkowej** są widoczne numery identyfikacji podatkowej, identyfikator odbiorcy, nazwa odbiorcy oraz firma, w której jest używany dany numer identyfikacji podatkowej. Odbiorcę można skopiować tylko wtedy, gdy znajduje się on w firmie, która nie jest bieżącą firmą. Po wybraniu odbiorcy spełniającego to kryterium wykonaj poniższe kroki.

1. Zostanie wyświetlona opcja **Kopiuj odbiorcę**. Domyślnie ta opcja ma wartość **Nie**. Aby skopiować odbiorcę do bieżącej firmy, ustaw dla tej opcji wartość **Tak**. 
2. Wybierz pozycję **Wybierz**. Zostanie otworzony nowy odbiorca.

