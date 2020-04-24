---
title: Przeliczanie jednostki miary dla wariantów produktów
description: W tym temacie wyjaśniono, jak skonfigurować przeliczanie jednostek miary dla wariantów produktu.
author: johanhoffmann
manager: tfehr
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: UnitOfMeasureConversion
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: e50be7fa6fa686a90b2dd5c5200c881e4629f019
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204500"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a>Przeliczanie jednostki miary dla wariantów produktów

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak skonfigurować przeliczanie jednostek miary dla wariantów produktu. Zawiera przykładową konfigurację.

Ta funkcja umożliwia firmom definiowanie różnych konwersji jednostek między wariantami tego samego produktu. W tym temacie używany jest poniższy przykład. Firma sprzedaje T-shirty w rozmiarach Small, Medium, Large, and Extra-Large. T-shirt jest definiowany jako produkt, a różne rozmiary są definiowane jako warianty produktu. T-shirty są pakowane w pudełka po pięć T-shirtów z wyjątkiem rozmiaru Extra-Large, których w pudełku mieści się tylko cztery. Firma chce śledzić różne warianty T-shirtów w jednostce **Sztuki**, ale sprzedaży T-shirty w jednostkach **Pudełka**. Konwersja między jednostką magazynową i jednostką sprzedaży to 1 pudełko = 5 sztuk, z wyjątkiem wariantu Extra-Large, w którym to przypadku konwersja to 1 pudełko = 4 sztuki.

### <a name="set-up-a-product-for-unit-conversion-per-variant"></a>Konfigurowanie produktu pod katem konwersji jednostek dla wariantu produktu

Warianty produktów można tworzyć dla produktów **Podtyp produktu**: **Produkt główny**. Aby uzyskać więcej informacji, zobacz temat [Tworzenie produktu głównego](tasks/create-product-master.md).

Funkcja nie jest włączona dla produktów, które są ustawiane dla procesów ilości efektywnej. 

Po utworzeniu produktu głównego z wariantami zwalnianych produktów można skonfigurować konwersje jednostek według wariantów. Element menu służący do otwierania strony konwersji jednostki można znaleźć w kontekście produktu lub wariantu produktu na następujących stronach.

-   Strona **Szczegóły produktu**
-   Strona **Szczegóły zwalnianych produktów**
-   Strona **Zwolnione warianty produktu**

Po otwarciu strony **Przeliczanie jednostek** w kontekście produktu głównego lub zwolnionego wariantu produktu możesz wybrać, czy chcesz skonfigurować konwersję jednostek dla produktu czy dla wariantu produktu. Można to zrobić zaznaczając opcję **Wariant produktu** lub **Produktu** na stronie **Tworzenie konwersji dla**.

### <a name="product-variant"></a>Wariant produktu

W przypadku wybrania opcji **Wariant produktu** można wybrać dla którego wariantu chcesz skonfigurować konwersję jednostek w polu **Wariant produktu**.

### <a name="product"></a>Produkt

W przypadku wybrania opcji **Produkt** można skonfigurować konwersję jednostek dla produktu głównego. Ta konwersja jednostki będzie stosowana do wszystkich wariantów produktu bez zdefiniowanej konwersji jednostki.

### <a name="example"></a>Przykład

Produkt główny **T-Shirt** ma cztery zwolnione warianty produktów: Small, Medium, Large i X-Large. T-shirty są pakowane w pudełka po pięć T-shirtów z wyjątkiem rozmiaru Extra-Large, których w pudełku mieści się tylko cztery.

Najpierw otwórz stronę **Przeliczanie jednostek** ze strony Szczegóły zwalniania produktu dla **T-shirt.**

Na stronie **Przeliczanie jednostek** ustaw konwersję jednostek dla wariantu zwolnienia produktu X-Large.

| **Field**             | **Ustawienie**             |
|-----------------------|-------------------------|
| Utwórz konwersję dla | Wariant produktu         |
| Wariant produktu       | T-Shirt : : X-Large : : |
| Od jednostki             | Pola                   |
| Współczynnik                | 4                       |
| Do jednostki               | Sztuki                  |

Warianty zwalniania produktów Small, Medium i Large mają tę samą konwersje jednostki między jednostkami Pudełko i Sztuki, co oznacza, że możesz zdefiniować jednostkę konwersji dla tych wariantów produktu w produkcie głównym.

| **Field**             | **Ustawienie** |
|-----------------------|-------------|
| Utwórz konwersję dla | Produkt     |
| Produkt               | T-Shirt     |
| Od jednostki             | Pola       |
| Współczynnik                | 5           |
| Do jednostki               | Sztuki      |

### <a name="using-excel-to-update-the-unit-conversions"></a>Aktualizowanie konwersji jednostek przy użyciu programu Excel

Jeśli produkt ma wiele wariantów produktu z różnymi konwersjami jednostek, dobrym rozwiązaniem jest eksportowanie jednostek konwersji ze strony **Przeliczanie jednostek** do arkusza kalkulacyjnego programu Excel, zaktualizowanie konwersji, a następnie opublikowanie ich ponownie w Supply Chain Mangement.

Opcję eksportowania do programu Excel i publikowania zmian z powrotem w Supply Chain Mangement włącza się z elementu menu **Otwórz w programie Microsoft office** w okienku akcji na stronie **Przeliczanie jednostek**.
