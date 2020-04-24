---
title: Producenci i modele składników majątku
description: W tym temacie wyjaśniono, jak konfigurować producentów składników majątku i pokrewne modele w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
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
ms.openlocfilehash: f2ef8a9afc007ce7e453f5e9cadfb912490545c0
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205122"
---
# <a name="asset-manufacturers-and-models"></a>Producenci i modele składników majątku

[!include [banner](../../includes/banner.md)]

 

W tym temacie wyjaśniono, jak konfigurować producentów składników majątku i pokrewne modele w module Zarządzanie składnikami majątku. Modele mogą być powiązane z typami składników majątku.

## <a name="set-up-product-model-relations"></a>Konfigurowanie relacji produkt-model

1. Wybierz kolejno **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Składniki majątku** \> **Producent i model**.
2. Wybierz opcję **Nowy**, aby utworzyć nowy produkt.
3. W polu **Producent** wprowadź nazwę producenta składnika majątku.
4. W polu **Opis wprowadź** opis.
5. Na skróconej karcie **Modele** wybierz opcję **Dodaj**, aby utworzyć model składnika majątku, który powinien być powiązany z producentem składnika majątku.
6. W polu **Model** wprowadź nazwę modelu składnika majątku.
7. W polu **Opis wprowadź** opis.
8. W polu **Typ składnika majątku** wybierz typ składnika majątku, z którym ma być powiązany model producenta.

    > [!NOTE]
    > Można również skonfigurować relacje dla typów składników majątku, producentów oraz modeli w wyszukiwaniu **Typy składników majątku**. Aby uzyskać więcej informacji, zobacz [Typy składników majątku](../setup-for-objects/object-types.md).

    Na skróconej karcie **Szczegóły** w polu **Modele** wyświetlana jest liczba modeli składników majątku, które są skonfigurowane na wybranym producencie składników majątku. W polu **Składniki majątku** wyświetlana jest liczba składników majątku korzystających z wybranego producenta.
    
    W polu **Składniki majątku** wyświetlana jest liczba obiektów korzystających z modelu producenta.

> [!NOTE]
> Typ składnika majątku może nie mieć relacji modelu producenta składnika majątku, może być powiązany z jednym modelem producenta składnika majątku lub może być powiązany z wieloma modelami producentów składników majątku. Jeśli typ składnika majątku jest powiązany z co najmniej jednym modelem producenta, tylko kombinacje skonfigurowane w wyszukiwaniu **Model producenta** mogą być wybrane na tych stronach Zarządzanie składnikami majątku, na których połączenie typu składnika majątku, producenta i modelu może być skonfigurowane. Te strony obejmują **Wszystkie składniki majątku**, **Poziomy usługi składnika majątku**, **Domyślne typy zadań** oraz **Wiersze budżetu konserwacji**. Jeśli niektóre typy składników majątku nie są powiązane z żadnym modelem producenta, na stronach są wyświetlane tylko te typy składników majątku i modele producenta, które również nie mają związku z typami składników majątku.

## <a name="select-a-manufacturer-and-model-on-an-object"></a>Wybieranie producenta i modelu na obiekcie

1. Wybierz kolejno **Zarządzanie składnikami majątku** \> **Wspólne** \> **Składniki majątku** \> **Wszystkie składniki majątku**.
2. W kolumnie **Składnik majątku** wybierz łącze dla składnika majątku. Zostanie wyświetlona strona **Szczegóły**.
3. Wybierz opcję **Edycja**.
4. Na skróconej karcie **Ogólne** wybierz wartości w polach **Producent** i **Model**.
