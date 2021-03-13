---
title: Projektowanie konfiguracji ER w celu pomijania znaków BOM w generowanych plikach
description: W tym temacie wyjaśniono, jak skonfigurować format raportowania elektronicznego (ER) w celu generowania raportów pomijających znaki typu znacznik kolejności bajtów (BOM).
author: NickSelin
manager: AnnBe
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 19fbbdea4bfdf30b1313a47e65056b536ed73dbe
ms.sourcegitcommit: 630a0b3f800f36ced49b79156dd52132904fef75
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2021
ms.locfileid: "5060826"
---
# <a name="design-er-configurations-to-suppress-bom-characters-in-generated-files"></a>Projektowanie konfiguracji ER w celu pomijania znaków BOM w generowanych plikach

[!include [banner](../includes/banner.md)]

Możesz w module [Raportowanie elektronicznej (ER)](general-electronic-reporting.md) zaprojektować [rozwiązanie](er-quick-start1-new-solution.md) do generowania dokumentów wychodzących. Aby wygenerować dokumenty jako pliki tekstowe lub XML, rozwiązanie musi zawierać [konfigurację](general-electronic-reporting.md#Configuration) ER zawierającą składnik [formatu](general-electronic-reporting.md#FormatComponentOutbound) ER. Aby określić [kodowanie znaków](https://docs.microsoft.com/windows/win32/intl/character-sets) reprezentujące zestaw znaków w generowanych plikach, format ER musi zawierać element formatu pliku **Wspólne\\Plik**. Aby skonfigurować składnik formatu ER, należy otworzyć [wersję roboczą](general-electronic-reporting.md#component-versioning) utworzonej konfiguracji ER w projektancie formatów ER i dodać element **Wspólne\\Plik**. W polu **Kodowanie** określ kodowanie plików wychodzących generowanych w czasie wykonywania za pomocą tego składnika.

> [!NOTE]
> Jeśli format zawiera niepoprawną nazwę kodowania, podczas zapisywania zmian ustawień formatu zgłaszany jest błąd.

![Dodawanie elementu głównego na stronie Projektant formatów](./media/er-suppress-bom-characters-image1.gif)

Jeśli wybierzesz kodowanie **UTF-8**, **UTF-16** lub **UTF-32**, opcja **Pomiń znaki BOM** stanie się dostępna. Ustaw tę opcję na wartość **Tak**, aby pomijać [znaki znaczników kolejności bajtów (BOM)](https://docs.microsoft.com/globalization/encoding/byte-order-mark) w plikach wychodzących, które są generowane w czasie wykonywania po uruchomieniu edytowalnego formatu ER.

> [!NOTE]
> Jeśli pole **Kodowanie** pozostanie puste, będzie używane domyślne kodowanie **UTF-8**.

![Ustawianie opcji Pomiń znaki BOM na stronie Projektant formatów](./media/er-suppress-bom-characters-image2.gif)

Aby przejrzeć funkcje w czasie wykonywania, należy wykonać odpowiednią procedurę. Na przykład wykonaj kroki w temacie [Odraczanie wykonania elementów XML w formatach ER](er-defer-xml-element.md). Po ukończeniu kroków z sekcji [Modyfikowanie formatu, aby obliczenie było oparte na wygenerowanych danych wyjściowych](er-defer-xml-element.md#modify-the-format-so-that-the-calculation-is-based-on-generated-output) tego tematu należy wykonać następujące dodatkowe kroki.

1. Określ kodowanie UTF:

    1. Wybierz element **Raport** typu **Wspólne\\Plik**.
    2. W polu **Kodowanie** określ kodowanie **UTF-8**.

2. Wygeneruj plik XML, który zawiera znak BOM:

    1. Ustaw opcję **Pomiń znaki BOM** na **Nie**, aby w generowanych plikach XML uwzględnić znaki BOM.
    2. Wykonaj kroki w sekcji [Odraczanie wykonania zbiorczego elementu XML, tak aby była używana obliczona suma](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) tematu [Odraczanie wykonania elementów XML w formatach ER](er-defer-xml-element.md) i zapisz wygenerowany plik jako **SampleXmlReport.xml**.

3. Wygeneruj plik XML, który nie zawiera znaku BOM:

    1. Ustaw opcję **Pomiń znaki BOM** na **Tak**, aby w generowanych plikach XML pomijać znaki BOM.
    2. Wykonaj kroki w sekcji [Odraczanie wykonania zbiorczego elementu XML, tak aby była używana obliczona suma](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) tematu [Odraczanie wykonania elementów XML w formatach ER](er-defer-xml-element.md) i zapisz wygenerowany plik jako **SampleXmlReport (1).xml**.

4. W narzędziu do porównywania plików porównaj wygenerowane pliki.

    Pierwsza różnica, która zostanie zauważona, znajduje się w nagłówku pliku. Plik SampleXmlReport.xml zawiera znak BOM, a plik SampleXmlReport (1).xml nie.

    ![Porównywanie wygenerowanych plików przy użyciu narzędzia do porównywania plików](./media/er-suppress-bom-characters-image3.png)

## <a name="see-also"></a>Informacje dodatkowe

- [Odłóż wykonanie elementów XML w formatach raportowania elektronicznego](er-defer-xml-element.md)
