---
title: Typy atrybutów konserwacji
description: W tym temacie wyjaśniono, jak tworzyć typy atrybutów w Zarządzaniu składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3b3247f693f5934b3fbf83b7b831c7ed221514cb
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783510"
---
# <a name="maintenance-attribute-types"></a>Typy atrybutów konserwacji

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

W tym temacie wyjaśniono, jak tworzyć typy atrybutów w Zarządzaniu składnikami majątku. Atrybuty są używane do opisywania właściwości różnych elementów. Można konfigurować atrybuty następujących elementów:

- [Typy lokalizacji czynności konserwacyjnych](../setup-for-functional-locations/functional-location-types.md)
- [Lokalizacje czynności konserwacyjnych](../functional-locations/create-functional-locations.md)
- [Typy składników majątku](../setup-for-objects/object-types.md)
- Środki trwałe

Atrybuty, które można skonfigurować różnią się w zależności od elementu. Na przykład dla lokalizacji czynności konserwacyjnych można skonfigurować atrybuty dla konfiguracji i fizycznego rozmiaru lokalizacji. Dla typu składnika majątku lub składnika majątku można skonfigurować atrybuty dla objętości silnika, zużycia energii i maksymalnej pojemności w różnych warunkach.

## <a name="create-attribute-types"></a>Tworzenie typu atrybutu

Tworzenie własnych typów atrybutów. Ponadto można przenosić wymiary produkty z Microsoft Dynamics 365 for Finance and Operations do strony **Typy atrybutów**.

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Typy atrybutów**.
2. Przy pierwszym ustawianiu typów atrybutów wybierz opcję **Utwórz wymiary produktu**, aby automatycznie przenieść standardowe wymiary produktu Finance and Operations.
3. Wybierz pozycję **Nowy**, aby utworzyć nowy typ atrybutu.
4. W polu **Typ atrybutu** wprowadź nazwę typu atrybutu.
5. W polu **Opis wprowadź** opis.
6. W polu **Jednostka** wybierz odpowiednią jednostkę atrybutu, zgodnie z wymaganiami.
7. W polu **Typ daty** wybierz typ daty dla jednostki.
8. Jeśli wybrano **Ciąg** jako typ danych, wykonaj następujące kroki, aby utworzyć wartości dla typu atrybutu:

    1. Wybierz typ atrybutu, a następnie wybierz **Wartości**.
    2. W polu **Wartości atrybutu** wybierz wartość **Nowa**.
    3. W polu **Typ atrybutu** wybierz typ atrybutu (wymiar).
    4. W polu **Wartość** wpisz wartość powiązaną.
    5. W polu **Opis wprowadź** opis.
    6. Zapisz rekord.
    7. Wróć do strony **Typy atrybutów**.

9. Zapisz rekord.

    Pole **Typy lokalizacji czynności konserwacyjnych** pokazuje liczbę lokalizacji funkcjonalnych, które używają typu atrybutu. Pole **Typy składników majątku** zawiera liczbę typów składników majątku, które są używane.
