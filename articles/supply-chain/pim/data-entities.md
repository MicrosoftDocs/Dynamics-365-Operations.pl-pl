---
title: Jednostki danych produktu
description: Ten temat zawiera informacje o różnych jednostkach, które mogą być używane do importowania i eksportowania danych produktu.
author: t-benebo
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: benebotg
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2019-12-1
ms.openlocfilehash: 2784e552d7984bbea9c74ad800c6305ab2a216e9
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7567158"
---
# <a name="product-data-entities"></a>Jednostki danych produktu

[!include [banner](../includes/banner.md)]

Aby importować i eksportować dane produktu, musisz używać jednostek danych. Poniższa tabela zawiera szczegółowe informacje dotyczące jednostek danych związanych z produktem i opisuje przeznaczenie każdej z nich.

| Jednostka | Nazwa (typ) drzewa obiektów aplikacji (AOT) | Notatki |
|--------|-------------------------------------------|-------|
| Produkty (wersja 2) | `EcoResProductV2Entity` | Ta jednostka jest używana do importowania i eksportowania produktów udostępnionych: odrębnych produktów i produktów głównych. Pozwala na aktualizacje. Nie obsługuje operacji SQL opartych na zestawie. Jest włączona dla protokołu Open Data Protocol (OData). |
| Zwolnione produkty (wersja 2) | `EcoResReleasedProductV2Entity` | Ta jednostka jest używana do importowania i eksportowania zwolnionych produktów udostępnionych: odrębnych produktów i produktów głównych. Pozwala na aktualizacje. Wymaga, aby udostępniony produkt został już utworzony. Po zaimportowaniu nowego zwolnionego produktu następuje zwolnienie produktu udostępnionego. Istnieją również oddzielne jednostki, które mogą być używane do importowania i eksportowania zwolnionych produktów głównych oraz zwolnionych odrębnych wariantów. Ta jednostka nie obsługuje operacji SQL na podstawie zestawu ani operacji usuwania. Jest włączona dla protokołu OData. |
| Tworzenie zwolnionego produktu (wersja 2) | `EcoResReleasedProductCreationV2Entity` | Ta jednostka jest używana do importowania produktów udostępnionych i produktów zwolnionych w jednym kroku. Mimo że obsługuje ona operacje eksportu, to użycie nie jest zalecane, ponieważ celem jednostki jest tworzenie produktu. Nie obsługuje aktualizacji. Obsługuje ograniczony zestaw pól (pola, które są dostępne w oknie dialogowym tworzenia produktu). Nie obsługuje operacji SQL opartych na zestawie. Nie jest ujawniana za pośrednictwem protokołu OData. |
| Warianty produktu | `EcoResProductVariantEntity` | Ta jednostka jest używana do importowania i eksportowania udostępnionych wariantów produktu. Pozwala na aktualizacje. Wymaga, aby wartości wymiarów zostały już utworzone. Kluczem integracji jest produkt główny oraz wymiary produktu. Ta jednostka nie obsługuje operacji SQL opartych na zestawie. Jest włączona dla protokołu OData. Obsługuje operacje usuwania. Nie można jej rozszerzyć przez dodanie nowych wymiarów produktu. |
| Warianty produktu według numeru identyfikacyjnego produktu | `EcoResProductNumberIdentifiedProductVariantEntity` | Ta jednostka jest używana do importowania i eksportowania udostępnionych wariantów produktu. Pozwala na aktualizacje. Wymaga, aby wartości wymiarów zostały już utworzone. Kluczem integracji jest numer produktu (a klucz integracji dla jednostki **Warianty produktu** jest produkt główny plus wymiary produktu). |
| Zwolnione warianty produktu | `EcoResReleasedProductVariantEntity` | Ta jednostka jest używana do importowania i eksportowania zwolnionych wariantów produktu. Pozwala na aktualizacje. Wymaga, aby udostępnione warianty produktu zostały już utworzone. Po zaimportowaniu nowego zwolnionego wariantu produktu następuje zwolnienie udostępnionego wariantu produktu. Ta jednostka nie obsługuje operacji SQL opartych na zestawie. Jest włączona dla protokołu OData. Mimo że obsługuje operacje usuwania, to użycie obecnie powoduje uszkodzenie danych z powodu usterki bieżącej platformy. Tej jednostki nie można rozszerzyć przez dodanie nowych wymiarów produktu. |
| Zwolnione warianty produktu według numeru identyfikacyjnego produktu | `EcoResProductNumberIdentifiedReleasedProductVariantEntity` | Ta jednostka przypomina jednostkę **Zwolnione warianty produktu**, ale kluczem integracji jest numer produktu, a nie produkt główny plus wymiary produktu. Można ją rozszerzyć przez dodanie nowych wymiarów produktu. |
| Zwolnione produkty możliwe do sprzedaży | `EcoResSellableReleasedProductEntity` | Ta jednostka jest używana do eksportowania tylko produktów, które można sprzedać. Produkty możliwe do sprzedaży to takie, które zawierają informacje wymagane w celu użycia w zamówieniu sprzedaży. Te same reguły mają zastosowanie podczas weryfikowania produktu przy użyciu funkcji **weryfikacji** na stronie **Zwolnione produkty**. |
| Zwolnione odrębne produkty (wersja 2) | `EcoResDistinctProductV2Entity` | Ta jednostka jest używana do eksportowania odrębnych produktów. Te odrębne produkty mogą być produktami, produktami podtypu i wariantami produktu. |
| Zwolnione produkty główne (wersja 2) | `EcoResProductMasterV2Entity` | Ta jednostka jest używana do importowania i eksportowania produktów głównych. Nie jest on włączona na potrzeby zarządzania danymi. |
| Kod kreskowy pozycji | `EcoResProductBarcodeEntityV3` | Ta jednostka jest używana do eksportowania produktów i kodów kreskowych. Ta jednostka nie zezwala na śledzenie zmian, aktualizowanie ani usuwanie. Aby można było skorzystać z funkcji śledzenia zmian, aktualizacji lub usuwania w postaci kodów kreskowych, należy skorzystać z **jednostki skojarzenie pozycja-kod kreskowy**. |
| Skojarzenie pozycja-kod kreskowy | `EcoResProductBarcodeAssociationEntity` | Ta jednostka jest używana do eksportowania produktów i kodów kreskowych. Umożliwia to śledzenie zmian, aktualizowanie i usuwanie. Aby można było skorzystać z tej jednostki, *udoskonalenia elementu funkcja — kod kreskowy* musi być włączony w module [Zarządzanie funkcjami ](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Jest to klucz jednostki `AssociationID`, który tworzy skojarzenie między kodem kreskowym a produktem. Aby można było dodać obsługę tego klucza, w momencie włączenia funkcji tabela `InventitemBarcodeAssociation` zostanie wypełniona dla istniejących kodów kreskowych towaru. Tabela jest wypełniana przy użyciu zadania wsadowego, a tabela kodów kreskowych zawiera dużą liczbę rekordów, co może zająć dużo czasu na wykonanie zadania wsadowego. Dlatego zalecamy zaplanowanie włączenia tej funkcji (i uruchomienie zadania wsadowego) w czasie odpowiadającym harmonogramowi biznesowemu. |
| Stany cyklu życia produktu | `EcoResProductLifecycleSateEntity` | Ta jednostka jest używana do importowania i eksportowania różnych stanów cyklu życia produktu, które można przypisać do produktu. |

> [!NOTE]
> Jednostki danych **Zwolnione produkty (wersja 2)** można używać do importowania produktów do systemu tylko wtedy, gdy udostępniony produkt został już utworzony. W przeciwnym razie, aby zaimportować produkty do systemu, należy użyć jednostki **Tworzenie produktu**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]