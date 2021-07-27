---
title: Zwalnianie wierszy BOM i wierszy formuły do magazynu
description: W tym temacie opisano proces zwalniania surowca dla wierszy BOM i formuły do magazynu.
author: johanhoffmann
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm, ProdParmReleaseToWarehouse, WHSReleaseToWarehouseProdBOM
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 99047bd30b04ccaaa24edbb2e28d5288ed2872f9
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6350553"
---
# <a name="release-bom-and-formula-lines-to-the-warehouse"></a>Zwalnianie wierszy BOM i wierszy formuły do magazynu

[!include [banner](../includes/banner.md)]

W tym temacie opisano proces zwalniania surowca dla wierszy listy składowej (BOM) i formuły do magazynu. Przy zwalnianiu wiersza BOM lub formuły do magazynu system najpierw określa, czy materiał jest już dostępny w lokalizacji wejściowej produkcji w zakładzie, gdzie materiał zostanie wykorzystany w procesie produkcji.

- Jeżeli materiał jest dostępny w lokalizacji wejściowej produkcji, jest pobierany z tej lokalizacji natychmiast po wydaniu sygnału zwolnienia materiału do magazynu.
- Jeżeli materiał nie jest dostępny w lokalizacji wejściowej produkcji, zwolnienie materiału wskazuje, że musi on zostać przeniesiony z lokalizacji w magazynie do lokalizacji wejściowej produkcji. Materiał jest przenoszony za pomocą pracy magazynu do pobierania surowca. Dlatego należy skonfigurować procesy pobierania surowca w magazynie. Aby uzyskać więcej informacji, zobacz [Omówienie uzupełniania zapasów](../warehousing/replenishment.md) i [Kontrola pracy magazynu za pomocą szablonów pracy i dyrektyw lokalizacji](../warehousing/control-warehouse-location-directives.md).

## <a name="methods-for-releasing-bom-and-formula-lines"></a>Metody zwalniania wierszy BOM i formuły

Zwalnianie wierszy BOM i formuły można skonfigurować tak, aby następowały jako część zwolnienia zlecenia produkcyjnego lub zamówienia partii. Zwolnienie można też kontrolować za pomocą zadania wsadowego lub wykonać jako interakcję ręczną.

Metoda używana do zwalniania wierszy BOM i formuły jest kontrolowana przez parametr **Zwolnienie wiersza produkcji**. Ten parametr jest dostępny w oknie **Kontrola produkcji** \> **Konfiguracja** \> **Parametry produkcji**.

- **Zwolnienie wierszy BOM i formuły w ramach zwalniania zlecenia produkcyjnego lub zamówienia partii** — w tej metodzie wiersze BOM i formuły dla produkcji lub zamówienia partii są zwalniane w ramach procesu zwalniania zamówienia. Zwykle podczas zwalniania zlecenia produkcyjnego lub zamówienia partii zadania produkcyjne są zwalniane do zakładu i drukowane są dokumenty produkcji. W tym procesie stan zamówienia zmienia się także na **Zwolnione**.
- **Zwolnienie wierszy BOM i formuły za pomocą zadania wsadowego lub jako interakcja ręczna** — w tej metodzie wiersze BOM i formuły można zwolnić tylko za pomocą zadania wsadowego **Automatyczne zwalnianie wierszy BOM i formuły** lub za pomocą interakcji ręcznej. Aby ręcznie zwolnić wiersze BOM i formuły, na stronie listy zlecenia produkcyjnego lub stronie szczegółów zlecenia produkcyjnego, w okienku akcji, wybierz opcję **Zwolnij do magazynu**.

Aby zapoznać się z szybką demonstracją zwalniania wierszy BOM i formuły do produkcji przy użyciu zadania wsadowego, obejrzyj ten krótki film na YouTube: [Wsadowe zwalnianie pobrania produkcji do magazynu](https://www.youtube.com/watch?v=8urAJn50dQ8).

## <a name="releasing-the-bom-and-formula-lines-by-using-a-batch-job"></a>Zwalnianie wierszy BOM i formuły za pomocą zadania wsadowego

Zadanie wsadowe **Automatyczne zwalnianie wierszy BOM i formuły** przechodzi przez wybrane wiersze BOM i formuły, które mają pozostałą ilość do zwolnienia. Zadanie uwzględnia tylko zamówienia, które mają stan **Zwolnione**, **Rozpoczęte** lub **Zgłoszone jako gotowe**. Jeżeli wiersz BOM lub formuły ma pozostała ilość do zwolnienia, zadanie zwalnia maksymalną ilość jaką można obsłużyć przez ilość już fizycznie zarezerwowaną i ilość, która jest fizycznie dostępna.

### <a name="example-of-a-batch-job-release"></a>Przykład zwolnienia zadania wsadowego

| Scenariusz | Pozostała ilość do zwolnienia | Ilość zarezerwowana fizycznie | Ilość dostępna fizycznie | Ilość zwolniona przez zadanie wsadowe |
|----------|-------------------------------|------------------------------|-------------------------------|------------------------------------|
| 1        | 100                           | 20                           | 90                            | 100                                |
| 2        | 100                           | 20                           | 70                            | 90                                 |
| 3        | 100                           | 0                            | 90                            | 90                                 |
| 4        | 100                           | 0                            | 110                           | 100                                |
| 5        | 100                           | 20                           | 0                             | 20                                 |

### <a name="batch-job-setup"></a>Konfiguracja zadania wsadowego

W kwerendzie zadania wsadowego **Automatyczne zwalnianie wierszy BOM i formuły** można skonfigurować kryterium filtra w celu określenia, ile dni wcześniej zadanie ma szukać wierszy, które mają niezwolnione ilości. W kwerendzie zadania, w polu **Data surowca** użyj funkcji **(LessThanDate())** jako kryterium filtra.

Na poniższej ilustracji przedstawiono zlecenie produkcyjne zawierające dwa zadania, 10 i 20, obejmujące montaż i pakowanie zlecenia produkcyjnego. Każde zadanie jest skonfigurowane w celu zużycia określonej ilości materiału. Na tej ilustracji horyzont czasowy zwalniania wskazany zieloną strzałką pod linią czasu równa się liczbie dni określonych w kryterium **(LessThanDate())**. Przykładowo **(LessThanDate(2))** oznacza, że zadanie powinno szukać niezwolnionych ilości tylko w horyzoncie czasowym wynoszącym dwa dni.

![Przykład zlecenia produkcyjnego zawierającego dwa zadania wsadowe.](media/bach-job-setup.PNG)

## <a name="releasing-material-per-operation-number-or-in-proportion-to-the-amount-of-finished-goods"></a>Zwalnianie materiału według numeru operacji lub proporcjonalnie do ilości wyrobów gotowych

Jeżeli materiały są zwalniane za pomocą ustawienia parametru **Podczas zwalniania zlecenia produkcyjnego** w przypadku zwalniania ręcznego dostępne są dwie opcje kontroli zwalniania materiału:

- Zwalnianie materiału według numeru operacji.
- Zwalnianie materiału proporcjonalnie do ilości wyrobów gotowych.

### <a name="release-material-per-operation-number"></a>Zwalnianie materiału według numeru operacji

Aby kontrolować operacje, do których ma być zwalniany materiał, użyj strony **Zwolnij do magazynu**.

- Wybierz opcję **Kontrola produkcji** \> **Zlecenia produkcyjne** \> **Wszystkie zlecenia produkcyjne**, wybierz zlecenie produkcyjne, a następnie na karcie **Magazyn** wybierz opcję **Zwolnij do magazynu**. Następnie użyj pól **Od nr operacji** i **Do nr operacji**, aby określić zakres numerów operacji.

Poniższa operacja przedstawia zlecenie produkcyjne zawierające dwie operacje, 10 i 20. W tym przykładzie, po ograniczeniu zwolnienia do operacji 10, zostanie zwolniony tylko materiał M9203.

![Przykład zwalniania materiału według numeru operacji.](media/two-operations.PNG)

Aby zapoznać się z szybką demonstracją zwalniania materiału proporcjonalnie do ilości wyrobów gotowych, obejrzyj ten krótki film na YouTube: [Ulepszenia procesu zwalniania zleceń produkcyjnych](https://www.youtube.com/watch?v=Rm3ojAz6Zu0).

### <a name="release-material-in-proportion-to-the-amount-of-finished-goods"></a>Zwalnianie materiału proporcjonalnie do ilości wyrobów gotowych

Surowiec można zwolnić dla częściowej ilości wyrobów gotowych lub w określonej jednostce.

- Aby zwolnić surowiec dla częściowej ilości wyrobów gotowych, wybierz opcję **Kontrola produkcji** \> **Zlecenia produkcyjne** \> **Wszystkie zlecenia produkcyjne**, wybierz zlecenie produkcyjne, a następnie na karcie **Magazyn** wybierz opcję **Zwolnij do magazynu**. Następnie wprowadź ilość w polu **Ilość**.

    Przykładowo, utworzono i zaplanowano zlecenie produkcyjne na 1000 sztuk (szt.). Kierownik zakładu produkcyjnego planuje produkcję 100 szt. podczas następnej zmiany i chce zwolnić materiały tylko dla tej zmiany. W tym przypadku kierownik może użyć pola **Ilość** do zwolnienia materiałów na 100 szt. planowanych na następną zmianę.

- Aby zwolnić surowiec w określonej jednostce, wybierz opcję **Kontrola produkcji** \> **Zlecenia produkcyjne** \> **Wszystkie zlecenia produkcyjne**, wybierz zlecenie produkcyjne, a następnie na karcie **Magazyn** wybierz opcję **Zwolnij do magazynu**. Następnie użyj pola **Jednostka**, aby wybrać jednostkę wyrobu gotowego, w której ma zostać zwolniony materiał.

    Dostępne jednostki są zdefiniowane w identyfikatorze grupy sekwencji jednostki wyrobu gotowego.

    Przykładowo, wyrób gotowy ma następującą konwersję jednostki z funtów (lbs.) na palety (PL): 1 PL = 100 funtów. Aby utworzyć zlecenie produkcyjne na 10 000 funtów wyrobów gotowych można zwolnić surowce na planowaną do produkcji liczbę palet. Wybierz **PL** jako jednostkę, a następnie wybierz odpowiednią liczbę w polu **Ilość**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]