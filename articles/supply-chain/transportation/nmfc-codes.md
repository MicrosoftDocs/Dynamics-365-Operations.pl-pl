---
title: Kody NMFC (National Motor Freight Classification)
description: W tym temacie opisano sposób pracy z kodami National Motor Freight Classification (NMFC) w systemie Microsoft Dynamics 365 Supply Chain Management
author: Henrikan
ms.date: 04/22/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 8e6aac6b3a8b730b6adc5c3d4410b98c3e8d5090eac866c337ed1d03409ba765
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6731158"
---
# <a name="national-motor-freight-classification-nmfc-codes"></a>Kody NMFC (National Motor Freight Classification)

[!include [banner](../includes/banner.md)]

Kody National Motor Freight Classification (NMFC) pomagają w klasyfikacji towarów, które mogą zostać wysłane. Kod NMFC jest oznaczeniem używanym do grupowania towarów. Umożliwia on firmom transportowym ocenianie towarów do wysyłki przez klasyfikowanie towarów na podstawie czynników takich jak dopasowanie ciężarówki, łatwość przeładunku i trwałość. Towary są grupowane w 18 klasach frachtu przy użyciu zakresu numerów od 50 do 500. Klasa przypisana do towaru opiera się na analizie czterech charakterystyk transportowych: gęstości, wymiarów, łatwości przeładunku i odpowiedzialności. Te cechy razem decydują o możliwości transportu towaru.

Kod NMFC jest kojarzony z każdą pozycji wysyłki mniejszą niż ładunek ciężarówki (Less Than Truckload — LTL). Na przykład komputer przenośny może mieć przypisaną klasę NMFC o klasie 2.5, a przewody elektryczne mogą mieć klasy NMFC o klasie 65.

Ta funkcja może ułatwić pracownikom używanie kodów NMFC do klasyfikowania pozycji wysyłki LTL. Oto kilka przykładów:

- Jeśli firma umieszcza opis frachtu w liście przewozowym, przewoźnik będzie mieć pojęcie, co transportuje. Fracht jest ważną klasyfikacją, ponieważ wiele firm transportowych opiera cały swój model biznesowy na typach frachtu, które przewożą.
- Ta klasyfikacja może być kluczowa dla firmy, ponieważ służy do określania kosztu danego ładunku.
- Firma może identyfikować rentowność firmy zajmującej się logistyką i transportem LTL.

W tym temacie opisano, jak pracować z kodami NMFC w systemie Microsoft Dynamics 365 Supply Chain Management.

## <a name="prerequisites"></a>Wymagania wstępne

Aby było można tworzyć kody NMFC, trzeba skonfigurować wszystkie klasy frachtu LTL, które muszą być mapowane na nie. Klasy frachtu LTL reprezentują kategorie towarów, podczas gdy kody NMFC są związane z określonymi towarami w każdej z 18 klas frachtu. Aby uzyskać więcej informacji na temat pracy z klasami LTL, zobacz [Klasy Less than truckload (LTL)](ltl-class.md).

## <a name="create-an-nmfc-code"></a>Tworzenie kodu NMFC

Aby utworzyć kod NMFC, wykonaj następujące czynności.

1. Wykonaj jeden z następujących kroków:

    - Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Zapasy \> Kody NMFC**.
    - Wybierz kolejno opcje **Zarządzanie transportem \> Ustawienia \> Standardy transportu \> Kody NMFC**.

1. Wybierz pozycję **Nowy**, aby utworzyć kod NMFC. Następnie ustaw wartości w następujących polach:

    - **Kod NMFC** — wprowadź kod NMFC typu towaru.
    - **Nazwa** — wprowadź nazwę kodu NMFC.
    - **Klasa LTL** — umożliwia wybór klasy LTL skojarzonej z kodem NMFC.
    - **jednostka załadunkowa BOL** — umożliwia określenie domyślnego typu załadunku wysyłki.

## <a name="example-set-up-nmfc-codes"></a>Przykładowa konfiguracja kodów NMFC

W poniższym przykładzie pokazano, jak skonfigurować dwa różne kody NMFC, które mogą być używane z różnymi produktami.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Zapasy \> Kody NMFC**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W nowym wierszu ustaw następujące wartości:

    - **Kod NMFC:** *92.5*
    - **Nazwa:** *komputery*
    - **Klasa LTL:** *92.5*
    - **Jednostka załadunkowa BOL:** *jednostka*

1. Na okienku akcji wybierz opcję **Zapisz**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W nowym wierszu ustaw następujące wartości:

    - **Kod NMFC:** *125*
    - **Nazwa:** *telefony*
    - **Klasa LTL:** *125*
    - **Jednostka załadunkowa BOL:** *jednostka*

1. Na okienku akcji wybierz opcję **Zapisz**.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Klasy ładunków częściowych (LTL)](ltl-class.md)
- [Tworzenie listu przewozowego](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
