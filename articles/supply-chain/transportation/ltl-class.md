---
title: Klasy ładunków częściowych (LTL)
description: W tym temacie objaśniono, czym są klasy ładunków częściowych (LTL) i jak je skonfigurować w systemie Microsoft Dynamics 365 Supply Chain Management.
author: Weijiesa
ms.date: 04/05/2021
ms.topic: article
ms.search.form: WHSLTLClass
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-04-05
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: a6e05ea7534ee081778a899d5956e6ca7cd104cb
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2022
ms.locfileid: "8678074"
---
# <a name="less-than-truckload-ltl-classes"></a>Klasy ładunków częściowych (LTL)

[!include [banner](../includes/banner.md)]

Klasa ładunków częściowych (LTL) jest klasą wysyłki frachtu używaną do klasyfikacji towarów, które mogą zostać wysłane. Każdy typ produktu lub asortymentu powinien mieć kod National Motor Freight Classification (NMFC) odpowiadający określonemu numerowi klasy frachtu dla wysyłek LTL. Klasy frachtu LTL reprezentują kategorie towarów, podczas gdy kody NMFC są związane z określonymi towarami w każdej z 18 klas frachtu.

Ta funkcja pozwala wykonać następujące zadania w systemie:

- Definiowanie klas frachtu LTL używanych w firmie.
- Przypisywanie klas LTL do kodu NMFC na stronie **Kody NMFC**. Aby uzyskać więcej informacji, zobacz temat [Kody National Motor Freight Classification (NMFC)](nmfc-codes.md).
- Przypisywanie kodu NMFC (razem ze skojarzonym z nim kodem LTL) do produktów na stronie **Produkty**.
- Precyzyjne ocenianie klasy LTL produktu, do którego jest przypisany kod NMFC.
- Określanie wymagań dotyczących pakowania klas LTL na podstawie międzynarodowych standardów LTL. W ten sposób zapewniasz, że twoje produkty będą dobrze chronione i na pewno zostaną wysłane.
- Dokładne szacowane kosztów wysyłki oparte na klasie frachtu LTL produktu.

W tym temacie opisano, jak tworzyć klasy LTL w systemie Microsoft Dynamics 365 Supply Chain Management.

## <a name="create-an-ltl-class"></a>Tworzenie klasy LTL

Aby utworzyć klasę LTL, wykonaj następujące czynności.

1. Wykonaj jeden z następujących kroków:

    - Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Zapasy \> Klasy LTL**.
    - Wybierz kolejno opcje **Zarządzanie transportem \> Ustawienia \> Standardy transportu \> Klasy LTL**.

2. W okienku akcji wybierz opcję **Nowe**, aby utworzyć klasę LTL. Następnie ustaw wartości w następujących polach:

    - **Klasa LTL** — służy do wprowadzania identyfikatora klasy LTL typu towaru. Większość firm korzysta ze standardu międzynarodowego. W takim przypadku wartość w tym polu będzie odpowiadać wartości w polu **Klasa**. Jeśli jednak firma używa własnego standardu, należy wprowadzić kod zgodny z tym standardem.
    - **Nazwa** — umożliwia wprowadzenie opisowej nazwy, która pomoże użytkownikom wybierać poprawną klasę LTL dla kodu NMFC.
    - **Klasa** — umożliwia wprowadzenie identyfikatora klasy LTL typu towaru zgodnej z międzynarodowym standardem. Wprowadzany tutaj kod musi być zgodny z oficjalnym standardem.

## <a name="example-set-up-ltl-classes"></a>Przykładowa konfiguracja klas LTL

W poniższym przykładzie pokazano, jak skonfigurować dwie różne klasy LTL, które mogą być używane z różnymi typami produktów.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Zapasy \> Klasy LTL**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W nowym wierszu ustaw następujące wartości:

    - **Klasa LTL:** *92.5*
    - **Nazwa:** *komputery, monitory, lodówki*
    - **Klasa:** *92.5*

1. Na okienku akcji wybierz opcję **Zapisz**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W nowym wierszu ustaw następujące wartości:

    - **Klasa LTL:** *125*
    - **Nazwa:** *małe artykuły gospodarstwa domowego*
    - **Klasa:** *125*

1. Na okienku akcji wybierz opcję **Zapisz**.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Kody NMFC (National Motor Freight Classification)](nmfc-codes.md)
- [Tworzenie listu przewozowego](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
