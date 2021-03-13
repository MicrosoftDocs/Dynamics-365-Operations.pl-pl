---
title: Konfigurowanie podatku dla zamówień online
description: Ten temat stanowi przegląd wyboru grupy podatków dla różnych typów zamówień w trybie online w Dynamics 365 Commerce.
author: gvrmohanreddy
manager: AnnBe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: gmohanv
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 56621bb9658b71551c7312aa47812903914bc888
ms.sourcegitcommit: da17648c296b22d517eadb2f71c7803672e5648d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/19/2021
ms.locfileid: "5031796"
---
# <a name="configure-sales-tax-for-online-orders"></a>Konfigurowanie podatku dla zamówień online

[!include [banner](includes/banner.md)]

Ten temat stanowi przegląd wyboru grupy podatków dla różnych typów zamówień w trybie online. 

Twój kanał handlu elektronicznego może chcieć obsługiwać takie opcje, jak dostawa lub odbiór zamówień online. Stosowanie podatku jest oparte na opcji wybranej przez użytkowników w trybie online. Jeśli klient witryny zdecyduje się kupić towar w trybie online i otrzymuje go na adres, podatek jest ustalany na podstawie ustawienia grupy podatków dla adresu wysyłkowego odbiorcy. Jeśli odbiorca zdecyduje się na odebranie zakupionego towaru w sklepie, podatek jest ustalany na podstawie ustawienia grupy podatków dla sklepu odbioru. 

## <a name="orders-shipped-to-a-customer-address"></a>Zamówienia wysłane na adres odbiorcy 

Na ogół podatki dla zamówień w trybie online, które są wysyłane na adresy odbiorców, są definiowane przez miejsce docelowe. Każda grupa podatków ma konfigurację podatku według lokalizacji docelowej sieci sprzedaży, w której firma może definiować szczegóły docelowe, takie jak powiat/region, województwo i miasto w postaci hierarchicznej. Po złożeniu zamówienia online aparat podatkowy Commerce używa adresu dostawy każdego elementu zamówienia w zamówieniu i znajduje grupy podatków z pasującymi kryteriami podatkowymi opartymi na miejscu docelowym. Na przykład w przypadku zamówienia online z adresem dostawy elementu zamówienia do San Francisco w Kalifornii aparat podatkowy znajdzie grupę podatków i kod podatku dla Kalifornii, a następnie odpowiednio obliczy podatek dla każdego elementu zamówienia.  

## <a name="customer-based-tax-groups"></a>Grupy podatków oparte na odbiorcach

W centrali Commerce istnieją dwa miejsca, w których skonfigurowano grupy podatków dla odbiorców:

- **Profil odbiorcy**
- **Adres wysyłkowy odbiorcy**

### <a name="if-a-customers-profile-has-a-tax-group-configured"></a>Jeśli profil odbiorcy ma skonfigurowaną grupę podatków

Rekord profilu odbiorcy w centrali może mieć skonfigurowaną grupę podatków, jednak w przypadku zamówień w trybie online grupa podatków skonfigurowana w profilu odbiorcy nie będzie używana przez aparat podatkowy. 

### <a name="if-a-customers-shipping-address-has-a-tax-group-configured"></a>Jeśli adres wysyłkowy odbiorcy ma skonfigurowaną grupę podatków

Jeśli rekord adresu wysyłkowego odbiorcy ma skonfigurowaną grupę podatków i zamówienie online (lub towar w wierszu) jest wysyłane na adres wysyłkowy odbiorcy, grupa podatków skonfigurowana w rekordzie adresu odbiorcy będzie używana przez aparat podatków do obliczania podatku.

#### <a name="configure-a-tax-group-for-a-customers-shipping-address-record"></a>Skonfiguruj grupę podatkową dla rekordu adresu wysyłkowego klienta

Aby skonfigurować grupę podatków dla rekordu adresu wysyłkowego odbiorcy w centrali Commerce, należy wykonać następujące kroki.

1. Przejdź do **Wszyscy odbiorcy**, a następnie wybierz żądanego odbiorcę. 
1. Na skróconej karcie **Adresy** wybierz żądany adres, a następnie wybierz **Więcej opcji \> Zaawansowane**. 
1. Na karcie **Ogólne**, na stronie **Zarządzanie adresami** ustaw wartość podatku zgodnie z potrzebą.

> [!NOTE]
> Grupa podatków jest definiowana przy użyciu adresu wysyłkowego wiersza zamówienia, a podatki oparte na miejscu docelowym są konfigurowane dla grupy podatków. Aby uzyskać więcej informacji, zajrzyj do [Konfigurowanie podatków dla sklepów internetowych w oparciu o miejsce docelowe](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).

## <a name="order-pickup-in-store"></a>Odbiór zamówienia w sklepie

W przypadku wierszy zamówienia z określonym odbiorem w sklepie lub przy krawężniku zostanie zastosowana grupa podatkowa z wybranego punktu odbioru. Aby uzyskać szczegółowe informacje dotyczące konfigurowania grupy podatków dla danego sklepu, zapoznaj się z tematem [Konfigurowanie innych opcji podatków dla sklepów](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).

> [!NOTE]
> Gdy wiersz zamówienia zostanie odebrany w sklepie, ustawienia podatkowe dotyczące adresu klienta (jeśli zostały skonfigurowane) zostaną zignorowane przez aparat podatkowy i zastosowana zostanie konfiguracja podatku sklepu odbioru. 

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie podatku](https://docs.microsoft.com/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=/dynamics365/commerce/toc.json) 

[Wybieranie metody obliczania podatku w polu Źródło](https://docs.microsoft.com/dynamics365/finance/general-ledger/sales-tax-calculation-methods-origin-field?toc=/dynamics365/commerce/toc.json) 

[ Przypisanie i zastąpienia podatku](https://docs.microsoft.com/dynamics365/supply-chain/procurement/tasks/sales-tax-assignment-overrides?toc=/dynamics365/commerce/toc.json) 

[Opcje Cała kwota i Obliczanie interwału dla kodów podatku](https://docs.microsoft.com/dynamics365/finance/general-ledger/whole-amount-interval-options-sales-tax-codes?toc=/dynamics365/commerce/toc.json) 

[Obliczanie zwolnienia z podatku](tax-exempt-price-inclusive.md) 

