---
title: Rozszerzanie jednostek danych dostępnych zapasów
description: W tym temacie przedstawiono przykład, który pokazuje, jak dodawać pola rozszerzone do widoków INVENTORSITEONHANDENTITY i INVENTWAREHOUSEONHANDENTITY, tak aby możliwości jednostek danych znajdujących się w magazynie mogły współpracować z rozszerzeniami.
author: sherry-zheng
manager: tfehr
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-07-27
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: e3bf3a7d48b0aa3e48845882be0ee86da17ed040
ms.sourcegitcommit: e276348a63bfdb9e712c0ea86e6c2a68c50872c0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "3665411"
---
# <a name="extend-inventory-on-hand-data-entities"></a><span data-ttu-id="dd334-103">Rozszerzanie jednostek danych dostępnych zapasów</span><span class="sxs-lookup"><span data-stu-id="dd334-103">Extend inventory on-hand data entities</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dd334-104">Microsoft Dynamics 365 Supply Chain Management oferuje funkcje [rozszerzalności](../../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md), które umożliwiają [dDodawanie pól do tabel za pośrednictwem rozszerzenia](../../fin-ops-core/dev-itpro/extensibility/add-field-extension).</span><span class="sxs-lookup"><span data-stu-id="dd334-104">Microsoft Dynamics 365 Supply Chain Management provides [extensibility](../../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md) features that let you [add fields to tables through extension](../../fin-ops-core/dev-itpro/extensibility/add-field-extension).</span></span> <span data-ttu-id="dd334-105">W tym temacie przedstawiono przykład, który pokazuje, jak dodawać pola rozszerzone do widoków `INVENTORSITEONHANDENTITY` i `INVENTWAREHOUSEONHANDENTITY`, tak aby możliwości jednostek danych znajdujących się w magazynie mogły współpracować z rozszerzeniami.</span><span class="sxs-lookup"><span data-stu-id="dd334-105">This topic provides an example that shows how to add extended fields to the `INVENTORSITEONHANDENTITY` and `INVENTWAREHOUSEONHANDENTITY` views, so that the capabilities of the inventory on-hand data entities can work with the extensions.</span></span> <span data-ttu-id="dd334-106">Aby uzyskać szczegółowe informacje o jednostkach danych, zapoznaj się z [omówieniem zarządzania danymi](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).</span><span class="sxs-lookup"><span data-stu-id="dd334-106">For more information about data entities, see [Data management overview](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).</span></span>

> [!NOTE]
> <span data-ttu-id="dd334-107">Poniżej znajduje się lista niektórych jednostek danych dostępnych zapasów:</span><span class="sxs-lookup"><span data-stu-id="dd334-107">Here is a list of some of the inventory on-hand data entities:</span></span>
>
> - <span data-ttu-id="dd334-108">Dostępne zapasy według oddziału</span><span class="sxs-lookup"><span data-stu-id="dd334-108">Inventory on-hand by site</span></span>
> - <span data-ttu-id="dd334-109">Dostępne zapasy według oddziału (wersja 2)</span><span class="sxs-lookup"><span data-stu-id="dd334-109">Inventory on-hand by site V2</span></span>
> - <span data-ttu-id="dd334-110">Dostępne zapasy według magazynu</span><span class="sxs-lookup"><span data-stu-id="dd334-110">Inventory on-hand by warehouse</span></span>
> - <span data-ttu-id="dd334-111">Dostępne zapasy według magazynu wersja 2</span><span class="sxs-lookup"><span data-stu-id="dd334-111">Inventory on-hand by warehouse v2</span></span>

<span data-ttu-id="dd334-112">Po dodaniu pól do tabel, które są używane przez widok `inventSiteOnHandView`, należy zsynchronizować aparat, aby rozszerzenia były rozpoznawane poprawnie.</span><span class="sxs-lookup"><span data-stu-id="dd334-112">After you add fields to tables that are used by the `inventSiteOnHandView` view, you must sync the engine so that the extensions are correctly recognized.</span></span>

1. <span data-ttu-id="dd334-113">Rozszerz widok `InventSiteOnHandView`, dodając pole rozszerzenie.</span><span class="sxs-lookup"><span data-stu-id="dd334-113">Extend the `InventSiteOnHandView` view by adding the extension field.</span></span>
1. <span data-ttu-id="dd334-114">Rozszerz widok `InventSiteOnHandAggregatedView` z polami rozszerzenia.</span><span class="sxs-lookup"><span data-stu-id="dd334-114">Extend the `InventSiteOnHandAggregatedView` view with the extension fields.</span></span>
1. <span data-ttu-id="dd334-115">Rozszerz klasę viewBuilder `InventSiteOnHandAggregatedViewBuilder`, modyfikując metodę `getExtensionFields()`.</span><span class="sxs-lookup"><span data-stu-id="dd334-115">Extend the `InventSiteOnHandAggregatedViewBuilder` viewBuilder class by modifying the `getExtensionFields()` method.</span></span> <span data-ttu-id="dd334-116">W ten sposób można mapować stare pola widoku na nowe pola widoku, gdy jest uruchamiana synchronizacja viewBuilder.</span><span class="sxs-lookup"><span data-stu-id="dd334-116">In this way, you map old view fields to new view fields when viewBuilder synchronization is run.</span></span>

<span data-ttu-id="dd334-117">Na przykład dodałeś następujące cztery pola do tabeli `InventTable` poprzez rozszerzenie:</span><span class="sxs-lookup"><span data-stu-id="dd334-117">For example, you've added the following four fields to the `InventTable` table through extension:</span></span>

- <span data-ttu-id="dd334-118">Pole niestandardowe 1</span><span class="sxs-lookup"><span data-stu-id="dd334-118">Custom field 1</span></span>
- <span data-ttu-id="dd334-119">Pole niestandardowe 2</span><span class="sxs-lookup"><span data-stu-id="dd334-119">Custom field 2</span></span>
- <span data-ttu-id="dd334-120">Pole niestandardowe 3</span><span class="sxs-lookup"><span data-stu-id="dd334-120">Custom field 3</span></span>
- <span data-ttu-id="dd334-121">Pole niestandardowe 4</span><span class="sxs-lookup"><span data-stu-id="dd334-121">Custom field 4</span></span>

<span data-ttu-id="dd334-122">W przypadku należy zmodyfikować metodę `getExtensionFields()` w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="dd334-122">In the case, you must modify the `getExtensionFields()` method in the following way.</span></span>

```xpp
[ExtensionOf(classStr(InventSiteOnHandAggregatedViewBuilder))]
public final class InventOnHandAggregatedViewBuilder\_Extension
{
    protected Map getExtensionFields()
    {
        next getExtensionFields();
        Map extensionFields = new Map(Types::Int64, Types::Int64);
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 1), fieldNum(InventSiteOnHandAggregatedView, Custom field 1));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 2), fieldNum(InventSiteOnHandAggregatedView, Custom field 2));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 3), fieldNum(InventSiteOnHandAggregatedView, Custom field 3));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 4), fieldNum(InventSiteOnHandAggregatedView, Custom field 4));
        return extensionFields;
    }
}
```

<span data-ttu-id="dd334-123">Po wykonaniu tych kroków można rozszerzyć dostępne zapasy zapasów według oddziału i dostępnych zapasów przez jednostki danych magazynu, dodając nowe pola.</span><span class="sxs-lookup"><span data-stu-id="dd334-123">After you complete these steps, you can extend the inventory on-hand by site and inventory on-hand by warehouse data entities by adding the new fields.</span></span> <span data-ttu-id="dd334-124">W ten sposób należy upewnić się, że rozszerzone pola są rozpoznawane i uwzględniane podczas migracji danych, w których są używane te jednostki danych.</span><span class="sxs-lookup"><span data-stu-id="dd334-124">In this way, you ensure that the extended fields are recognized and included during data migration that uses those data entities.</span></span>
