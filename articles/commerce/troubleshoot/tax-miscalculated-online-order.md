---
title: Podatki w zamówieniach online są niepoprawnie obliczone
description: Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w nieprawidłowym obliczaniu podatków od zamówień online lub gdy grupa podatków w wierszu sprzedaży nie jest poprawnie ustawiona.
author: Reza-Assadi
ms.date: 02/16/2022
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
ms.openlocfilehash: eefcfc983a7b3861caa4b4362d2813082b7963a6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901628"
---
# <a name="taxes-on-online-orders-are-incorrectly-calculated"></a>Podatki w zamówieniach online są niepoprawnie obliczone

[!include [banner](../../includes/banner.md)]

Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w nieprawidłowym obliczaniu podatków od zamówień online lub gdy grupa podatków w wierszu sprzedaży nie jest poprawnie ustawiona.

## <a name="description"></a>opis

Po umieszczeniu zamówienia w sieci e-commerce podatki są niepoprawnie obliczone lub grupa podatków w wierszu sprzedaży jest niepoprawnie ustawiona.

## <a name="resolution"></a>Rozwiązanie

### <a name="configure-general-sales-tax-groups-in-commerce-headquarters"></a>Konfigurowanie ogólnych grup podatków w programie Commerce Headquarters

Aby skonfigurować ogólne grupy podatków w Commerce headquarters, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Podatek \> Podatki pośrednie \> Podatek \> Grupy podatków**.
1. W lewym okienku nawigacji wybierz grupę podatków do skonfigurowania.
1. Na skróconej karcie **Podatek oparty na lokalizacji detalicznej** skonfiguruj podatki dla grupy podatków.

> [!NOTE]
> W przypadku wysyłki, która nie obejmuje podatku od sprzedaży, który jest określany na podstawie adresu klienta, adres dostawy wiersza i podatki od miejsca docelowego skonfigurowane dla grupy podatkowej określają grupę podatków. Aby uzyskać więcej informacji, zajrzyj do [Konfigurowanie podatków dla sklepów internetowych w oparciu o miejsce docelowe](/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).

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

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie podatku dla zamówień online](../sales-tax-config.md)
