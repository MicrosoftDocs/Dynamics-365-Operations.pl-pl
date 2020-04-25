---
title: Typy atrybutów konserwacji
description: W tym temacie wyjaśniono, jak tworzyć typy atrybutów w Zarządzaniu składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2ed333a3064654691966eac3c20626955ada0030
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205904"
---
# <a name="maintenance-attribute-types"></a>Typy atrybutów konserwacji

[!include [banner](../../includes/banner.md)]

 

W tym temacie wyjaśniono, jak tworzyć typy atrybutów w Zarządzaniu składnikami majątku. Atrybuty są używane do opisywania właściwości różnych elementów. Można konfigurować atrybuty następujących elementów:

- [Typy lokalizacji czynności konserwacyjnych](../setup-for-functional-locations/functional-location-types.md)
- [Tworzenie lokalizacji czynności konserwacyjnych](../functional-locations/create-functional-locations.md)
- [Typy składników majątku](../setup-for-objects/object-types.md)
- Składniki majątku

Atrybuty, które można skonfigurować różnią się w zależności od elementu. Na przykład dla lokalizacji czynności konserwacyjnych można skonfigurować atrybuty dla konfiguracji i fizycznego rozmiaru lokalizacji. Dla typu składnika majątku lub składnika majątku można skonfigurować atrybuty dla objętości silnika, zużycia energii i maksymalnej pojemności w różnych warunkach.

## <a name="create-attribute-types"></a>Tworzenie typu atrybutu

Tworzenie własnych typów atrybutów. Ponadto można przenosić wymiary produkty do strony **Typy atrybutów**.

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Typy atrybutów**.
2. Przy pierwszym ustawianiu typów atrybutów wybierz opcję **Utwórz wymiary produktu**, aby automatycznie przenieść standardowe wymiary produktu.
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
