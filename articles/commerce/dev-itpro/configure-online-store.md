---
title: Konfigurowanie sklepów internetowych
description: Ten artykuł zawiera łącza do tematów, które pomogą centralnie konfigurować i zarządzać sklepem internetowym.
author: kfend
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: 31541
ms.assetid: 7a25f9b4-a0bb-4e8c-95c0-c0799ec0620d
ms.search.region: Global
ms.author: meeram
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: cf7adf76cb547ffbf516ce475380ddafaca1dfc6
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5215469"
---
# <a name="configure-online-stores"></a>Konfigurowanie sklepów internetowych

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera łącza do tematów, które pomogą centralnie konfigurować i zarządzać sklepem internetowym.

Tematy wymienione w tabeli poniżej pomagają skonfigurować składniki modułu Commerce oraz sklep internetowy na komputerze klienckim.

## <a name="configure-an-online-store"></a>Konfigurowanie sklepu internetowego

| Zadanie                                                | Szczegóły                                                                                                                                                                                                                                                                                                                                                   | Tematy                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|-----------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Konfiguruj składniki.                        | Konfigurowanie informacji operacji handlu i zarządzanie nimi. Informacje te dotyczą sklepów, podatków, produktów, kart upominkowych, promocji i rabatów.                                                                                                                                                                                                          | [Konfigurowanie i obsługiwanie modułu Retail](https://technet.microsoft.com/library/hh597201.aspx) (materiał w serwisie TechNet dla systemu Microsoft Dynamics AX 2012)                                                                                                                                                                                                                                                                                          |
| Konfigurowanie hierarchii nawigacji w kanale.    | Tworzenie hierarchii kategorii nawigacji w kanale w celu ustanowienia struktury kategorii dla produktów, które oferujesz przez sklep internetowy. Definiujesz hierarchię kategorii, a następnie przypisujesz produkty, grupy atrybutów produktów i wartości atrybutów do kategorii. Następnie należy przypisać hierarchię kategorii do sklepu internetowego.                            | [Konfigurowanie hierarchii modułu detalicznego](https://technet.microsoft.com/library/hh580593.aspx)</br> (Zawartość w witrynie TechNet dla AX 2012)</br> [Ustawianie atrybutów i typów atrybutów](https://technet.microsoft.com/library/hh227548.aspx) (zawartość w witrynie TechNet dla AX 2012)</br> [Ustawianie grup atrybutów sieci sprzedaży](https://technet.microsoft.com/library/jj728713.aspx) (zawartość w witrynie TechNet dla AX 2012) |
| Dodawanie sklepu internetowego do hierarchii organizacyjnej | Zanim będzie można przypisać asortyment produktów lub realizować zamówienia dla utworzonego sklepu internetowego, lub generować raporty zawierające informacje z tego sklepu, należy przypisać sklep do jednej lub więcej hierarchii organizacyjnych. Na poziomie minimum, należy przypisać sklep internetowy do hierarchii organizacyjnej, która zawiera asortymenty produktów. | [Konfigurowanie sklepu internetowego](https://technet.microsoft.com/library/jj682095.aspx) (materiał w serwisie TechNet dla systemu AX 2012)                                                                                                                                                                                                                                                                                                     |
| Dodawanie metod dostawy do sklepu internetowego          | Wybór metod dostawy, które będą oferowane przez sklep internetowy.                                                                                                                                                                                                                                                                                                 | [Konfigurowanie sklepu internetowego](https://technet.microsoft.com/library/jj682095.aspx) (materiał w serwisie TechNet dla systemu AX 2012)                                                                                                                                                                                                                                                                                                     |
| Mapowanie atrybutów i dodawanie metadanych                   | Wybór opcji wskazujących, jak atrybuty dla każdej kategorii lub kanału produktu powinny zachowywać się w sklepie internetowym w witrynie Microsoft SharePoint.                                                                                                                                                                                              | [Konfigurowanie sklepu internetowego](https://technet.microsoft.com/library/jj682095.aspx) (materiał w serwisie TechNet dla systemu AX 2012)                                                                                                                                                                                                                                                                                                     |

## <a name="configure-online-store-products"></a>Konfigurowanie produktów sklepu internetowego

| Zadanie                                 | Szczegóły                                                                                                                                           | Tematy                                                                                                                                                                                                                                                                            |
|--------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Dodawanie asortymentów do sklepu internetowego | Dodawanie asortymentu zawierającego produkty oferowane w sklepie internetowym.                                                                  | [Konfigurowanie sklepu internetowego](https://technet.microsoft.com/library/jj682095.aspx) (materiał w serwisie TechNet dla systemu AX 2012)                                                                                                                                              |
| Zarządzanie katalogami                     | Za pomocą katalogów produktów można identyfikować produkty, które chcesz oferować w swoich sklepach.                                                              | [Najważniejsze zadania: tworzenie katalogów produktów sieci sprzedaży](https://technet.microsoft.com/library/jj728712.aspx) (materiał w serwisie TechNet dla systemu AX 2012)                                                                                                                           |
| Zarządzanie cenami                       | Konfigurowanie i używanie grup cenowych, które są centralnym łącznikiem między cenami i rabatami a kanałami, katalogami, przynależnościami i programami lojalnościowymi. | [Konfigurowanie cen za pomocą grup cenowych](https://technet.microsoft.com/library/hh597169.aspx) (zawartość w witrynie TechNet dla AX 2012)</br> [Ustawianie podatków](https://technet.microsoft.com/library/hh580571.aspx) (zawartość w witrynie TechNet dla AX 2012) |
| Zarządzanie rabatami                    | Możesz skonfigurować korekty cen i cztery rodzaje rabatów oraz nimi zarządzać.                                                                                  | [Konfigurowanie korekt cen i rabatów](https://technet.microsoft.com/library/hh597114.aspx) (materiał w serwisie TechNet dla systemu AX 2012)                                                                                                                          |
| Zarządzanie opłatami transportowymi             | Konfigurowanie opłat transportowych specyficznych dla sklepu internetowego i zarządzanie nimi.                                                                     | [Konfigurowanie opłat transportowych w sklepach internetowych](https://technet.microsoft.com/library/jj728714.aspx) (materiał w serwisie TechNet dla systemu AX 2012)                                                                                                                           |
| Zarządzanie metodami dostawy            | Zarządzanie metodami dostawy oferowanymi w sklepach internetowych.                                                                                        | [Konfigurowanie metod dostawy](https://technet.microsoft.com/library/jj728719.aspx) (materiał w serwisie TechNet dla systemu AX 2012)                                                                                                                                            |

## <a name="set-up-data-exchange-between-commerce-and-the-online-store"></a>Konfigurowanie wymiany danych między Commerce a sklepem internetowym

| Zadanie                                 | Szczegóły                                                                                                                               | Tematy                                                                                                                                                                                                                                                                                  |
|--------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Konfigurowanie profil integracji kanałów | Profile umożliwiają składnikom komunikowanie się między sobą. Profile należy skonfigurować przed skonfigurowaniem ustawień wymiany danych. | [Konfigurowanie usługi Real-time Service](https://technet.microsoft.com/library/hh580631.aspx) (zawartość w witrynie TechNet dla AX 2012)</br> [Konfigurowanie profilu kanału](https://technet.microsoft.com/library/jj677402.aspx) (zawartość w witrynie TechNet dla AX 2012) |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]