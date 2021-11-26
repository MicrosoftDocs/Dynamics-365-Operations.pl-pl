---
title: Przykłady i logika raportu wartości zapasów
description: Ten temat zawiera kilka przykładów wyników, które są prezentowane w każdym typie raportu o wartości zapasów. Raporty wartości zapasów zawierają szczegółowe informacje dotyczące ilości i kwot fizycznych oraz finansowych zapasów.
author: banluo-ms
ms.date: 10/19/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: banluo
ms.search.validFrom: 2021-10-19
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 4ad85058c8743895185d3da2e8975711f1e3bc2c
ms.sourcegitcommit: ba10ba2cd4fb4267afb5aacae4f6a52aa2456e7e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2021
ms.locfileid: "7798396"
---
# <a name="inventory-value-report-examples-and-logic"></a>Przykłady i logika raportu wartości zapasów

[!include [banner](../includes/banner.md)]

Raporty wartości zapasów zawierają szczegółowe informacje dotyczące ilości i kwot fizycznych oraz finansowych zapasów. Ten temat zawiera kilka przykładów wyników, które są prezentowane w każdym typie raportu o wartości zapasów.

Aby uzyskać więcej informacji na temat generowania i używania poszczególnych typów raportów wartości zapasów, zobacz [raporty wartości zapasów](inventory-value-report-storage.md).

## <a name="sample-data-that-is-used-in-these-examples"></a>Przykładowe dane używane w tych przykładach

Przykłady przedstawione w tym temacie są oparte na przykładowych danych transakcji magazynowych opisanych w tej sekcji.

### <a name="storage-dimension-setup"></a>Konfiguracja wymiarów magazynowania

Przykładowy system zawiera następujące ustawienia wymiarów magazynowania:

| Imię i nazwisko | Aktywna | Magazyn | Magazyn finansowy |
|---|---|---|---|
| Oddział | Tak | Tak | Tak |
| Magazyn | Tak | Tak | Nie |

### <a name="inventory-model"></a>Model magazynu

W przypadku systemu przykładowego model magazynu dla zwolnionych produktów to *FIFO*, a pole **Koszt własny** dla modelu magazynu to *Włączanie wartości fizycznej*.

### <a name="inventory-transactions"></a>Transakcje magazynowe

Przykładowy system zawiera następujące transakcje magazynowe dla zwolnionego produktu o numerze towaru *B0001*.

| Odwołanie | Oddział | Magazyn | Pokwitowanie | Problem | Data fizycznej transakcji | Data finansowa | Ilość | Kwota kosztu | Fizyczna wartość kosztu |
|---|---|---|---|---|---|---|---|---|---|
| Zamówienie zakupu | 1 | 11 | Zakupione | | 15 marca | 15 marca | 10 | 1 000 | 1 000 |
| Zamówienie zakupu | 2 | 21 | Zakupione | | 15 marca | 15 marca | 10 | 2,000 | 2,000 |
| Zamówienie zakupu | 1 | 11 | Odebrane | | 15 kwietnia | | 5 | | 375 |
| Zamówienie przeniesienia | 1 | 11 | | Sprzedane | 2 maja | 2 maja | -5 | -458,33 | -458,33 |
| Zamówienie przeniesienia | 1 | 12 | Zakupione | | 2 maja | 2 maja | 5 | 458.33 | 458.33 |
| Zamówienie sprzedaży | 1 | 12 | | Sprzedane | 3 maja | 3 maja | -1 | -91,67 | -91,67 |

### <a name="inventory-value-report-configuration"></a>Konfiguracja raportu wartości zapasów

Przykładowy system zawiera konfigurację raportu wartości zapasów, która ma następujące ustawienia:

- **Zakres:**  *Data księgowania*
- **Magazyn:** *Tak*
- **Oblicz średni koszt jednostkowy:** *Tak*
- **Łączna ilość i wartość:** *Tak*
- **Oddział, widok:** *Wybrane*
- **Identyfikator zasobu, widok:** *Tak*
- **Poziom:** *Sumy*

## <a name="inventory-value-report-example-1"></a>Przykład raportu wartości zapasów 1

W poniższej tabeli i ilustracjach przedstawiono wyniki użycia przykładowych danych i konfiguracji raportu opisanych wcześniej w tym temacie.

| Typ zasobu | Zasób | Oddział | Odwołanie | Zapasy: ilość finansowa | Zapasy: kwota finansowa | Zapasy: zaksięgowana ilość fizyczna | Zapasy: zaksięgowana kwota fizyczna | Zapasy: ilość | Zapasy: kwota | Średni koszt jednostkowy |
|---|---|---|---|---|---|---|---|---|---|---|
| Materiał | B0001 | 1 | Saldo końcowe | 9.00 | 908.33 | 5.00 | 375.00 | 14.00 | 1,283.33 | 91.67 |
| Materiał | B0001 | 2 | Saldo końcowe | 10,00 | 2,000.00 | 0,00 | 0,00 | 10,00 | 2,000.00 | 200.00 |

### <a name="standard-inventory-value-report-for-example-1"></a>Standardowy raport wartości zapasów, na przykład 1

Na poniższej ilustracji przedstawiono standardowy **raport wartości zapasów** dla przykładu 1. (Aby otworzyć większą wersję, należy wybrać ilustrację).

[![Raport wartości zapasów dla przykładu 1.](media/inventory-value-report-ex1-small.png "Raport wartości zapasów dla przykładu 1")](media/inventory-value-report-ex1.png)

### <a name="inventory-value-report-storage-report-for-example-1"></a>Zapoznaj się z raportem dotyczącym przechowywania raportu wartości zapasów dla przykładu 1

Na poniższej ilustracji przedstawiono standardowy **Przechowywanie raportu wartości zapasów** dla przykładu 1. (Aby otworzyć większą wersję, należy wybrać ilustrację).

[![Zapoznaj się z raportem dotyczącym przechowywania raportu wartości zapasów dla przykładu 1.](media/inventory-value-report-storage-ex1-small.png "Zapoznaj się z raportem dotyczącym przechowywania raportu wartości zapasów dla przykładu 1")](media/inventory-value-report-storage-ex1.png)

## <a name="inventory-value-report-example-2"></a>Przykład raportu wartości zapasów 2

Na poniższych tabelach i ilustracjach przedstawiono wyniki użycia przykładowych danych opisanych wcześniej w tym temacie, ale po uruchomieniu raportu wartość pola **Poziom** została ustawiona na *Transakcje* w konfiguracji raportu. Po uruchomieniu raportu w polu **Od dnia** ustawiono wartość *15 marca*.

| Typ zasobu | Zasób | Oddział | Data | Identyfikator | Odwołanie | Zapasy: ilość finansowa | Zapasy: kwota finansowa | Zapasy: zaksięgowana ilość fizyczna | Zapasy: zaksięgowana kwota fizyczna | Zapasy: ilość | Zapasy: kwota |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Materiał | B0001 | 1 | 15/03/2021 | 00000126 | Zamówienie zakupu | 0,00 | 0,00 | 10,00 | 1,000.00 | **10.00** | **1,000.00** |
| Materiał | B0001 | 1 | 15/03/2021 | 00000126 | Zamówienie zakupu | 10,00 | 1,000.00 | -10,00 | -1000,00 | **0.00** | **0.00** |
| Materiał | B0001 | 1 | 15/04/2021 | 00000128 | Zamówienie zakupu | 0,00 | 0,00 | 5.00 | 375.00 | **5.00** | **375.00** |
| Materiał | B0001 | 1 | 2/05/2021 | 000003 | Wysyłka zamówienia przeniesienia | -5,00 | -458,33 | 0,00 | 0,00 | **-5,00** | **-458,33** |
| Materiał | B0001 | 1 | 2/05/2021 | 000003 | Przyjęcie zamówienia przeniesienia | 5.00 | 458.33 | 0,00 | 0,00 | **5.00** | **458.33** |
| Materiał | B0001 | 1 | 3/05/2021 | 000835 | Zamówienie sprzedaży | 0,00 | 0,00 | -1,00 | -91,67 | **-1,00** | **-91,67** |
| Materiał | B0001 | 1 | 3/05/2021 | 000835 | Zamówienie sprzedaży | -1,00 | -91,67 | 1,00 | 91.67 | **0.00** | **0.00** |
| Materiał | B0001 | 2 | 15/03/2021 | 00000127 | Zamówienie zakupu | 0,00 | 0,00 | 10,00 | 2,000.00 | **10.00** | **2,000.00** |
| Materiał | B0001 | 2 | 15/03/2021 | 00000127 | Zamówienie zakupu | 10,00 | 2,000.00 | -10,00 | -2000,00 | **0.00** | **0.00** |
| Materiał | B0001 | 2 | 2/05/2021 | 000003 | Wysyłka zamówienia przeniesienia | 5.00 | 458.33 | 0,00 | 0,00 | **5.00** | **458.33** |
| Materiał | B0001 | 2 | 2/05/2021 | 000003 | Przyjęcie zamówienia przeniesienia | -5,00 | -458,33 | 0,00 | 0,00 | **-5,00** | **-458,33** |

### <a name="standard-inventory-value-report-for-example-2"></a>Standardowy raport wartości zapasów dla przykładu 2

Na poniższej ilustracji przedstawiono standardowy **raport wartości zapasów** dla przykładu 2. (Aby otworzyć większą wersję, należy wybrać ilustrację).

[![Raport wartości zapasów dla przykładu 2.](media/inventory-value-report-ex2-small.png "Raport wartości zapasów dla przykładu 2")](media/inventory-value-report-ex2.png)

### <a name="inventory-value-report-storage-report-for-example-2"></a>Zapoznaj się z raportem dotyczącym przechowywania raportu wartości zapasów dla przykładu 2

Na poniższej ilustracji przedstawiono standardowy **Przechowywanie raportu wartości zapasów** dla przykładu 2. (Aby otworzyć większą wersję, należy wybrać ilustrację).

[![Zapoznaj się z raportem dotyczącym przechowywania raportu wartości zapasów dla przykładu 2.](media/inventory-value-report-storage-ex2-small.png "Zapoznaj się z raportem dotyczącym przechowywania raportu wartości zapasów dla przykładu 2")](media/inventory-value-report-storage-ex2.png)

## <a name="inventory-value-report-example-3"></a>Przykład raportu wartości zapasów 3

Zaleca się uruchamianie raportów wartości zapasów po ponownej inwentaryzacji lub zamknięciu magazynu, tak aby transakcje i kwoty były na nie wpływały podczas ponownego przeliczania lub zamykania magazynu.

W poniższych podsekcjach są wyświetlane raporty wartości zapasów wygenerowane po zamknięciu magazynu do 30 maja.

### <a name="example-3-when-the-totals-level-is-used"></a>Przykład 3 w przypadku korzystania z poziomu sum

W poniższej tabeli przedstawiono wyniki w przypadku użycia przykładowych danych i konfiguracji raportu opisanych wcześniej w tym temacie. (W tej konfiguracji raportu jest to **Pole** poziomu ma wartość *Sumy*.)

| Typ zasobu | Zasób | Oddział | Odwołanie | Zapasy: ilość finansowa | Zapasy: kwota finansowa | Zapasy: zaksięgowana ilość fizyczna | Zapasy: zaksięgowana kwota fizyczna | Zapasy: ilość | Zapasy: kwota | Średni koszt jednostkowy |
|---|---|---|---|---|---|---|---|---|---|---|
| Materiał | B0001 | 1 | Saldo końcowe | 9.00 | 900.00 | 5.00 | 375.00 | 14.00 | 1,275.00 | 91.07 |
| Materiał | B0001 | 2 | Saldo końcowe | 10,00 | 2,000.00 | 0,00 | 0,00 | 10,00 | 2,000.00 | 200.00 |

### <a name="example-3-when-the-transactions-level-is-used"></a>Przykład 3, gdy używany jest poziom Transakcje

W poniższej tabeli przedstawiono wyniki użycia przykładowych danych opisanych wcześniej w tym temacie, ale wartość pola **Poziom** została zmienić na *Transakcje* w konfiguracji raportu.

| Typ zasobu | Zasób | Oddział | Data | Identyfikator | Odwołanie | Zapasy: ilość finansowa | Zapasy: kwota finansowa | Zapasy: zaksięgowana ilość fizyczna | Zapasy: zaksięgowana kwota fizyczna | Zapasy: ilość | Zapasy: kwota |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Materiał | B0001 | 1 | 15/03/2021 | 00000126 | Zamówienie zakupu | 0,00 | 0,00 | 10,00 | 1,000.00 | 10,00 | 1,000.00 |
| Materiał | B0001 | 1 | 15/03/2021 | 00000126 | Zamówienie zakupu | 10,00 | 1,000.00 | -10,00 | -1000,00 | 0,00 | 0,00 |
| Materiał | B0001 | 1 | 15/04/2021 | 00000128 | Zamówienie zakupu | 0,00 | 0,00 | 5.00 | 375.00 | 5.00 | 375.00 |
| Materiał | B0001 | 1 | 2/05/2021 | 000003 | Wysyłka zamówienia przeniesienia | -5,00 | -458,33 | 0,00 | 0,00 | -5,00 | -458,33 |
| Materiał | B0001 | 1 | 2/05/2021 | 000003 | Przyjęcie zamówienia przeniesienia | 5.00 | 458.33 | 0,00 | 0,00 | 5.00 | 458.33 |
| Materiał | B0001 | 1 | 3/05/2021 | 000835 | Zamówienie sprzedaży | 0,00 | 0,00 | -1,00 | -91,67 | -1,00 | -91,67 |
| Materiał | B0001 | 1 | 3/05/2021 | 000835 | Zamówienie sprzedaży | -1,00 | -91,67 | 1,00 | 91.67 | 0,00 | 0,00 |
| Materiał | B0001 | 1 | 31/05/2021 | 000835 | Zamówienie sprzedaży | 0,00 | -8,33 | 0,00 | 0,00 | 0,00 | -8,33 |
| Materiał | B0001 | 1 | 31/05/2021 | 000003 | Wysyłka zamówienia przeniesienia | 0,00 | -41,67 | 0,00 | 0,00 | 0,00 | -41,67 |
| Materiał | B0001 | 1 | 31/05/2021 | 000003 | Przyjęcie zamówienia przeniesienia | 0,00 | 41.67 | 0,00 | 0,00 | 0,00 | 41.67 |
| Materiał | B0001 | 2 | 15/03/2021 | 00000127 | Zamówienie zakupu | 0,00 | 0,00 | 10,00 | 2,000.00 | 10,00 | 2,000.00 |
| Materiał | B0001 | 2 | 15/03/2021 | 00000127 | Zamówienie zakupu | 10,00 | 2,000.00 | -10,00 | -2000,00 | 0,00 | 0,00 |
| Materiał | B0001 | 2 | 2/05/2021 | 000003 | Wysyłka zamówienia przeniesienia | 5.00 | 458.33 | 0,00 | 0,00 | 5.00 | 458.33 |
| Materiał | B0001 | 2 | 2/05/2021 | 000003 | Przyjęcie zamówienia przeniesienia | -5,00 | -458,33 | 0,00 | 0,00 | -5,00 | -458,33 |
| Materiał | B0001 | 2 | 31/05/2021 | 000003 | Wysyłka zamówienia przeniesienia | 0,00 | 41.67 | 0,00 | 0,00 | 0,00 | 41.67 |
| Materiał | B0001 | 2 | 31/05/2021 | 000003 | Przyjęcie zamówienia przeniesienia | 0,00 | -41,67 | 0,00 | 0,00 | 0,00 | -41,67 |
