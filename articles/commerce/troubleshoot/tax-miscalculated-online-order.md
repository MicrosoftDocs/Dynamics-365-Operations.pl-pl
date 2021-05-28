---
title: Podatki w zamówieniach online są niepoprawnie obliczone
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w nieprawidłowym obliczniu podatków od zamówień online lub gdy grupa podatków w wierszu sprzedaży nie jest poprawnie ustawiona.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f7cef533d76bdddfbad2e8c5f84f81ef62bccc38
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021110"
---
# <a name="taxes-on-online-orders-are-incorrectly-calculated"></a>Podatki w zamówieniach online są niepoprawnie obliczone

[!include [banner](../../includes/banner.md)]

Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w nieprawidłowym obliczniu podatków od zamówień online lub gdy grupa podatków w wierszu sprzedaży nie jest poprawnie ustawiona.

## <a name="description"></a>opis

Po umieszczeniu zamówienia w sieci e-commerce podatki są niepoprawnie obliczone lub grupa podatków w wierszu sprzedaży jest niepoprawnie ustawiona.

## <a name="resolution"></a>Rozdzielczość

### <a name="configure-the-sales-tax-for-a-retail-store-in-commerce-headquarters"></a>Konfigurowanie podatku dla sklepu detalicznego w programie Commerce Headquarters

Aby skonfigurować podatek od sprzedaży dla sklepu detalicznego w siedzibie Commerce, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Handel detaliczny i inny \> Kanały \> Wszystkie sklepy**.
1. Wybierz sklep, dla który ma zostać skonfigurowany podatek.
1. Na skróconej karcie **Ogólne** w sekcji **Podatek** skonfiguruj informacje o podatku dla sklepu.

> [!NOTE]
> W przypadku pobrania produktu ze sklepu grupa podatków pochodzi ze sklepu wybranego do pobrania. Aby uzyskać więcej informacji, zobacz [Ustawianie innych opcji podatków dla sklepów](/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).

### <a name="configure-the-sales-tax-for-a-customers-address-in-commerce-headquarters"></a>Skonfiguruj podatek od sprzedaży dla adresu klienta w siedzibie Commerce

Aby skonfigurować podatek od sprzedaży dla adresu klienta w siedzibie Commerce, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy**.
1. Wybierz klienta, dla którego chcesz skonfigurować podatki od sprzedaży.
1. Na skróconej karcie **Adresy** wybierz adres, dla których chcesz skonfigurować podatki, wybierz opcję **Więcej opcji**, a następnie wybierz opcję **Zaawansowane**.
1. Na karcie **Ogólne** wybierz **Grupa podatków**.
1. W polu **Podatek** wybierz odpowiednią wartość.

> [!NOTE]
> W przypadku wysyłki, która obejmuje podatek w adresie odbiorcy, adres dostawy wiersza określa grupę podatków dla wiersza. Jeśli odbiorca wysyła przesyłkę na istniejący adres, który ma już skonfigurowaną grupę podatków, używana będzie istniejąca grupa podatku. Domyślnie podczas tworzenia adresów nie ma grupy podatków.

### <a name="configure-general-sales-tax-groups-in-commerce-headquarters"></a>Konfigurowanie ogólnych grup podatków w programie Commerce Headquarters

Aby skonfigurować ogólne grupy podatków w Commerce headquarters, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Podatek \> Podatki pośrednie \> Podatek \> Grupy podatków**.
1. W lewym okienku wybierz grupę podatków do skonfigurowania.
1. Na skróconej karcie **Podatek oparty na lokalizacji detalicznej** skonfiguruj podatki dla grupy podatków.

> [!NOTE]
> W przypadku wysyłki, która nie obejmuje podatku w adresie odbiorcy, grupa podatków określa adres dostawy wiersza oraz podatki oparte na lokalizacji docelowej, które są skonfigurowane dla grupy podatków. Aby uzyskać więcej informacji, zajrzyj do [Konfigurowanie podatków dla sklepów internetowych w oparciu o miejsce docelowe](/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie podatku dla zamówień online](../sales-tax-config.md)