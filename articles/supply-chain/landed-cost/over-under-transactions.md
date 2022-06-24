---
title: Transakcje z nadwyżką/niedoborem
description: Ten artykuł zawiera informacje, które pomogą w skonfigurowaniu szczegółów zasad dotyczących transakcji nadwyżki/niedoboru, tak aby system mógł określić, jak zarządzać nadmiernym i niepełnym przetwarzaniem towarów w momencie ich przyjęcia.
author: Weijiesa
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMOverUnderTrans, ITMOverUnderToleranceTable, ITMOverUnderReasonTable, ITMOverUnderToleranceGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 79ce18a462f9c2f93dceec82da7ee0209ab61f78
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845005"
---
# <a name="overunder-transactions"></a>Transakcje z nadwyżką/niedoborem

[!include [banner](../../includes/banner.md)]

Gdy zamówienia w transporcie są przetwarzane, system oczekuje, że ilość towaru, która jest odbierana w docelowym magazynie do zużycia, będzie zgodna z ilością określoną w wierszach zamówienia zakupu, które są skojarzone z podróżą. Jednak ponieważ dokładna ilość w wierszach zamówienia zakupu nie zawsze jest odebrana w magazynie, moduł **Koszt z wyładunkiem** definiuje zestaw reguł, które są używane do obsługi nadbierania i niedobierania towarów. Te reguły są szczególnie ważne, ponieważ oryginalne zamówienie zakupu zostało zafakturowane i nie można go już modyfikować. Konfigurując szczegóły zasad transakcji powyżej / poniżej, umożliwiasz systemowi określenie, w jaki sposób zarządzać nadmiernym i niepełnym przetwarzaniem towarów w momencie ich przyjęcia. Można także ręcznie zarządzać zapasami i ich zapasami, korzystając ze strony **Transakcje nadwyżki/niedoboru**.

## <a name="overunder-tolerances"></a>Tolerancje nadwyżki/niedoboru

Ustawiasz tolerancje nadmiernych i niedostatecznych dostaw, aby określić nadmierne i niedostateczne ilości lub objętości, które mogą być przetworzone podczas podróży bez powodowania błędu. Jeżeli odbiór rejsu znajduje się poza tymi tolerancjami, musi zostać zmodyfikowany i rozwiązany przed zamknięciem linii rejsu w celu dalszego przetwarzania.

Aby skonfigurować tolerancje, przejdź do tematu **Koszt z wyładunkiem \> Konfiguracja nadwyżki/niedoboru \> Tolerancja nadwyżki/niedoboru**. Możesz tam przeglądać, edytować, dodawać i usuwać rekordy tolerancji. W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.

| Pole | opis |
|---|---|
| Kod konta | <p>Umożliwia zdefiniowanie zakresu dostawców, których dotyczy tolerancja, przez wybranie jednej z następujących wartości:</p><ul><li>**Tabela** – tolerancja na nadwyżki/niedoboru dotyczy tylko dostawcy wybranego dla wiersza.</li><li>**Grupa** – tolerancja na nadwyżki/niedoboru dotyczy wszystkich dostawców w grupie tolerancji dostawcy wybranej dla wiersza.</li><li>**Wszystkie** – Tolerancja nadwyżki/niedoboru dotyczy wszystkich dostawców.</li></ul> |
| Relacja konta | W zależności od wartości wybranej w polu **Kod konta** wybierz dostawcę lub grupę dostawców, których dotyczy tolerancja nadwyżki/niedoboru. |
| Kod pozycji | <p>Umożliwia zdefiniowanie zakresu pozycji, których dotyczy tolerancja, przez wybranie jednej z następujących wartości:</p><ul><li>**Tabela** – tolerancja na nadwyżki/niedoboru dotyczy tylko pozycje wybranego dla wiersza.</li><li>**Grupa** – tolerancja na nadwyżki/niedoboru dotyczy wszystkich towarów w grupie tolerancji towaru wybranej dla wiersza.</li><li>**Wszystkie** – Tolerancja nadwyżki/niedoboru dotyczy wszystkich pozycji.</li></ul> |
| Relacja produktu | Wybierz towar lub grupę towarów, do których ma zastosowanie tolerancja nadwyżki/niedoboru, w zależności od wartości wybranej w polu **Kod towaru**. |
| Tolerancja kwoty | Umożliwia wprowadzenie tolerancji kwoty, która powinna zostać zastosowana do całego zamówienia zakupu. |
| Tolerancja wartości procentowej | Wprowadź procentową tolerancję, którą należy zastosować do pojedynczego wiersza zamówienia zakupu. |

## <a name="overunder-reasons"></a>Przyczyny nadwyżki/niedoboru

Jeśli z otrzymaną linią rejsu powiązana jest nadmierna lub niedostateczna ilość, może być konieczne zidentyfikowanie przyczyny nadmiernej lub niedostatecznej ilości. W takim przypadku możesz wybrać powód nadwyżki lub niedostatecznej dostawy w wierszu odbioru po otrzymaniu towarów.

Aby skonfigurować przyczyny nadmiernej lub niepełnej dostawy, przejdź do **Koszt z wyładunkiem \> Konfiguracja nadwyżki/niedoboru \> Powody nadwyżki/niedoboru**. Możesz tam przeglądać, edytować, dodawać i usuwać dostępne przyczyny nadmiernej i niedostatecznej dostawy. W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego powodu.

| Pole | opis |
|---|---|
| Przyczyna nadwyżki/niedoboru | Umożliwia wprowadzenie unikatowej nazwy dla przyczyny transakcji dotyczącej nadwyżki lub niedoboru. |
| opis | Służy do wprowadzania opisu przyczyny nadwyżki/niedoboru. |
| Transakcje | Wybierz arkusz ruchu skojarzony z przyczyną nadwyżki/niedoboru. To pole zawiera listę wszystkich dostępnych arkuszy, z które jest skojarzony typ arkusza *Ruch* na stronie **Nazwy arkuszy magazynowych** (**Konfiguracja zarządzania zapasami \> Nazwy arkuszy \> Zapasy**). |

## <a name="item-overunder-tolerance-groups"></a>Grupy rozbieżności nadwyżki/niedoboru pozycji

Towary o podobnych tolerancjach można grupować. W ten sposób można ustawić tolerancję nadwyżki/niedoboru dla wszystkich towarów w tej grupie jednocześnie.

Aby skonfigurować grupy tolerancji nadwyżki/niedoboru, przejdź do, przejdź do **Koszt z wyładunkiem \> Konfiguracja nadwyżki/niedoboru \> Grupy tolerancji nadwyżki/niedoboru pozycji**. Możesz tam przeglądać, edytować, dodawać i usuwać rekordy grup tolerancji nadwyżki/niedoboru. W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.

| Pole | opis |
|---|---|
| Grupa tolerancji nadwyżki/niedoboru | Wprowadź unikatową nazwę grupy. Wybierz nazwę opisującą tolerancję, na przykład *1% Var*. |
| opis | Służy do wprowadzania opisu grupy. |

## <a name="vendor-overunder-tolerance-groups"></a>Grupy tolerancji nadwyżki/niedoboru dostawcy

Można zgrupować dostawców, którzy regularnie dostarczają z nadwyżką lub niedoborem. Następnie można ustawić tolerancję nadwyżki/niedoboru dla grupy.

Aby skonfigurować grupy tolerancji nadwyżki/niedoboru dostawcy, przejdź do, przejdź do **Koszt z wyładunkiem \> Konfiguracja nadwyżki/niedoboru \> Grupy tolerancji nadwyżki/niedoboru dostawcy**. Możesz tam przeglądać, edytować, dodawać i usuwać rekordy grup tolerancji nadwyżki/niedoboru. W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.

| Pole | opis |
|---|---|
| Grupy nadwyżki/niedoboru | Wprowadź unikatową nazwę grupy. Wybierz nazwę opisującą typ dostawców należących do grupy. |
| opis | Służy do wprowadzania opisu grupy. |

## <a name="view-and-process-overunder-transactions"></a>Wyświetlanie i przetwarzanie transakcji nadwyżki/niedoboru

Transakcje nadwyżki i niedoboru są generowane, gdy ilość odłożonych towarów nie jest równa z zainicjowaną ilością. Ilość w arkuszu przybycia powinna być aktualizowana tylko ilość odłożona.

Podczas przetwarzania przyjęcia wierszy podróży dla dostawcy można ustawić tolerancje nadwyżki/niedoboru. Następnie elementy zostaną przejęte i zweryfikowane. Tolerancję można ustawić jako wartość procentową, kwotę lokalną lub obie wartości.

Jeśli odebrany towar znajduje się w granicach tolerancji, system wygeneruje arkusz ruchu. Ten arkusz można określić na stronie parametrów podróży. Ponadto zostanie utworzona transakcja na nadwyżki/niedoboru. Na przykład wartość zamówienia jest $100, wartość przyjęcia jest $99 i te wartości spełniają reguły tolerancji. W takim przypadku zostanie utworzony ujemny arkusz magazynowy dla ilości niedoboru.

Jeśli odebrany towar jest poza tolerancją, system wygeneruje transakcję na nadwyżki/niedobory dla różnicy ilości.

Aby wyświetlić i przetworzyć transakcje nadwyżki/niedoboru, przejdź do **Koszt z wyładunkiem \> Zapytania \> Transakcje nadwyżki/niedoboru**. Tam transakcja nadwyżki/niedoboru zostanie powiązana ze wszystkimi pozycjami w rejsie, które zostały odebrane z nadwyżką lub z niedostatecznym poziomem. Zaleca się użycie strony **Transakcje nadwyżki/niedoboru** w celu rozwiązania wszystkich transakcji nadwyżki/niedoboru, które są skojarzone z podróżą. **Nie** zaleca się także ręcznego rozwiązywania transakcji magazynowych z dostawami magazynowych za pomocą arkuszy ruchu lub inwentaryzacji. Zamiast tego do zarządzania ilościami w magazynach z dostawą należy użyć strony **Transakcje nadwyżki/niedoboru**.

### <a name="upper-overview-tab"></a>Karta Przegląd górny

Aby wyświetlić transakcje nadwyżki/niedoboru, wybierz kartę **Przegląd** w górnej części strony **Transakcje nadwyżki/niedoboru**. W poniższej tabeli opisano pola dostępne w siatce.

| Pole | opis |
|---|---|
| Identyfikator transakcji z nadwyżką/niedoborem | Unikatowa nazwa rekordu transakcji nadwyżki/niedoboru, utworzona automatycznie podczas przetwarzania arkusza przybycia. |
| Podróż | Podróży, do których został dołączony wiersz zakupu. |
| Kontener wysyłkowy | Kontener, do którego został dołączony wiersz zakupu. |
| Arkusz przyjęcia | Arkusz przybycia, na podstawie którego wygenerowano wiersz „nadwyżki/niedoboru”. |
| Odwołanie | Odwołanie do zamówienia zakupu lub zamówienia przeniesienia skojarzonego z transakcją nadwyżki/niedoboru. |
| Identyfikator | Zamówienie zakupu, do którego odwołuje się transakcja nadwyżki/niedoboru. |
| Konto dostawcy | Dostawca, z którym związana jest nadwyżka lub niedobór. |
| Identyfikator towaru w drodze | Numer towarów w drodze, jeśli ma zastosowanie. |
| Numer towaru | Numer pozycji, z którym związana jest nadwyżka lub niedobór. |
| Ilość oryginalna | Oryginalna ilość z wiersza zamówienia, który jest dołączony do przesyłki. |
| Przyjęta ilość | Ilość, która została faktycznie odebrana. |
| Różnica | Różnica między oczekiwaną kwotą w arkuszu przybycia a kwotą zaksięgowaną w arkuszu przybycia. Wartość ujemna oznacza nadmierną dostawę towarów. |
| Pozostała ilość | Ilość, która pozostaje w wierszu arkusza przybycia. |
| Nadwyżka/niedobór w dostawie | Wartość wskazująca, czy otrzymana ilość jest powyżej czy poniżej. |
| Stan | Pokazuje stan transakcji nadwyżki/niedoboru. W zależności od ustawień na stronie **[Parametry kosztów z wyładunkiem](landed-cost-parameters.md)** nadwyżka dostawy może automatycznie utworzyć arkusz ruchu dla kwoty nadwyżki dostawy i zaksięgować arkusz. W takim przypadku transakcja nadwyżki/niedoboru będzie mieć stan *Zakończono*. Jeśli akcja jest wymagana do przeniesienia towarów z magazynu z dostawą z niedoborem, rekord będzie miał stan *W trakcie*. |
| Przyczyna nadwyżki/niedoboru | Powód związany z transakcją nadwyżki/niedoboru. |
| Inne wymiary magazynowe | Kolumny dla dodatkowych wymiarów można wyświetlać w wymaganych wymiarach w siatce. Wymiary te obejmują numer partii, stan zapasów i magazyn. W okienku akcji wybierz **Zapasy \> Wyświetl wymiary**, aby otworzyć okno dialogowe, w którym można wybrać wymiary, które mają zostać dołączyć. |

### <a name="upper-general-tab"></a>Górna karta ogólne

Aby wyświetlić więcej informacji o wierszu aktualnie wybranym na górnej karcie **Przegląd**, wybierz kartę **Ogólne** w górnej części strony **Transakcje nadwyżki/niedoboru**. Informacje na tej karcie zawierają wartości wszystkich dostępnych wymiarów. Ta informacja jest ciągnięta z pochodzących z pochodzących zamówień zakupu.

### <a name="lower-overview-tab"></a>Dolna karta Przegląd

Aby wyświetlić typ dokumentu dla wiersza wybranego w górnej części karty **Przegląd**, wybierz kartę **Przegląd** w dolnej części strony **Transakcje nadwyżki/niedoboru**. W poniższej tabeli przedstawiono dostępne pola.

| Pole | opis |
|---|---|
| Nowy typ dokumentu | To pole jest ustawiane jako *Arkusz transakcji* lub *Zamówienie zakupu*, w zależności od akcji, która jest pokazywana w wybranym wierszu transakcji nadwyżki/niedoboru. |
| Identyfikator | Odniesienie i łącze do zamówienia zakupu lub arkusza przesunięcia skojarzonego z wybranym wierszem transakcji nadwyżki/niedoboru. |
| Przyczyna nadwyżki/niedoboru | Powód związany z wybranym wierszem transakcji nadwyżki/niedoboru. |
| Ilość | Ilość wybrana dla zamówienia zakupu lub arkusza przesunięcia skojarzonego z wybranym wierszem transakcji nadwyżki/niedoboru. |

### <a name="lower-general-tab"></a>Dolna karta ogólne

Aby wyświetlić numer transakcji nadwyżki/niedoboru, identyfikator partii i numer wymiaru skojarzony z wybranym wierszem transakcji nadwyżki/niedoboru, wybierz kartę **Ogólne** w dolnej części strony **Transakcje nadwyżki/niedoboru**. 

### <a name="process-overunder-transactions"></a>Przetwarzanie transakcji nadwyżki/niedoboru

Okienko akcji na stronie **Transakcje nadwyżki/niedoboru** zawiera następujące polecenia przetwarzania transakcji wybranych na stronie. Każde polecenie umożliwia wybór sposobu przetwarzania każdej transakcji.

- **Utwórz \> Ruch** – utworzenie i zaksięgowanie arkusza transakcji dla wybranej transakcji. W przypadku transakcji niedoboru automatycznie tworzony i księgowany jest arkusz transakcji z różnicą między oczekiwaną a rzeczywistą ilością otrzymaną. To polecenie należy zaznaczyć w przypadku transakcji nadwyżki, jeśli dostawca ma zrealizować różnicę kosztów.
- **Utwórz \> Zamówienie zakupu** – Utwórz zamówienie zakupu dla różnicy między oczekiwaną a rzeczywistą otrzymaną ilością wybranej transakcji. Wybierz to polecenie dla transakcji nadwyżki, jeśli Twoja organizacja zauważy różnicę w kosztach.
- **Utwórz \> Przeniesienie do lokalizacji docelowej** – Polecenie dotyczy tylko zamówień przeniesienia. To pole należy zaznaczyć, aby przenieść ilość nadwyżki lub niedoboru do magazynu docelowego.
- **Utwórz \> Przeniesienie do lokalizacji pochodzenia** – Polecenie dotyczy tylko zamówień przeniesienia. To pole należy zaznaczyć, aby przenieść ilość nadwyżki lub niedoboru do magazynu pochodzenia.
