---
title: Moduł zameldowania do odbioru
description: W tym artykule omówiono moduł zameldowania do odbioru i wyjaśniono, jak go skonfigurować w systemie Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 7002db893da1802063148a9b800ffa92f3e5f065
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885482"
---
# <a name="check-in-for-pickup-module"></a>Moduł zameldowania do odbioru

[!include [banner](includes/banner.md)]

W tym artykule omówiono moduł zameldowania do odbioru i wyjaśniono, jak go skonfigurować w systemie Microsoft Dynamics 365 Commerce.

Moduł zameldowania do odbioru zawiera stronę potwierdzenia dla odbiorców korzystających z niestandardowych funkcji ewidencjonowania odbiorcy Dynamics 365 Commerce, aby powiadomić sklep o swoim przybyciu. Moduł zameldowania do odbioru umożliwia również skonfigurowanie formularza, który zbiera dodatkowe informacje od odbiorców w celu ułatwienia dostawy zamówienia. Informacje te obejmują numer miejsca parkingowego odbiorcy oraz marki i modelu jego pojazdu. 

## <a name="module-properties"></a>Właściwości modułu

| Nazwa właściwości | Wartości | opis |
|---------------|--------|-------------|
| Tekst potwierdzenia | Ciąg tekstowy | Zawartość nagłówka widoczna na stronie potwierdzenia zameldowania. |
| Pokaż kod QR | **Prawda** lub **Fałsz** | Gdy właściwość ma wartość **Prawda**, na stronie potwierdzenia zameldowania jest wyświetlony kod QR, który reprezentuje identyfikator potwierdzenia zamówienia. |
| Nagłówek dodatkowych informacji | Ciąg tekstowy | Zawartość nagłówka wyświetlana po skonfigurowaniu pól dodatkowych informacji. |
| Klucze informacji dodatkowych | Para wartości Identyfikator zasobu / Zasób | Każdy klucz tworzy pole formularza i skojarzoną z nim etykietę, która służy do zbierania dodatkowych informacji od odbiorców. |
| Klucze dodatkowych informacji \> Identyfikator zasobu | Ciąg tekstowy | Każda informacja tworzy pole formularza i skojarzoną z nim etykietę, która służy do zbierania dodatkowych informacji od odbiorców. Ta właściwość identyfikuje klucz informacji dodatkowych. W zadaniu utworzonym w punkcie sprzedaży (POS) wartość tej właściwości jest pokazywana jako etykieta w polu instrukcji. |
| Klucze dodatkowych informacji \> Wartość zasobu | Ciąg tekstowy | Etykieta pola tekstowego w zadaniu w punkcie sprzedaży. |
| Klucze dodatkowych informacji \> Wymagane | **Prawda** lub **Fałsz** | Ta właściwość określa, czy odbiorcy muszą wypełnić pole formularza, aby kontynuować. Gdy właściwość ma wartość **Prawda**, przy etykiecie formularza jest renderowana gwiazdka, a sprawdzanie wartości null uniemożliwia kontynuowanie, dopóki odbiorca nie wprowadzi wartości. |

## <a name="add-the-check-in-for-pickup-module-to-a-page"></a>Dodawanie modułu zameldowania do odbioru do strony

Moduł zameldowania do odbioru należy dodać na nowej stronie, która jest tworzona w celu potwierdzenia zameldowania. Ta strona będzie stanowić środowisko zatwierdzania zameldowania dla odbiorców, którzy wybiorą łącze lub przycisk **Jestem tutaj** w swojej wiadomości e-mail. 

## <a name="configure-the-additional-information-form"></a>Konfigurowanie formularza informacji dodatkowych

Domyślnie jeśli nie skonfigurowano kluczy dodatkowych informacji, moduł wyświetla odbiorcy stronę zatwierdzenia zameldowania. Po wyświetleniu zatwierdzenia zameldowania w punkcie sprzedaży sklepu, w którym zamówienie jest odbierane, jest tworzone zamówienie.

Po skonfigurowaniu jednego lub większej liczby kluczy dodatkowych informacji odbiorcy są najpierw monitowane o wprowadzenie informacji. Gdy wybiorą opcję **Prześlij**, zostanie wyświetlone potwierdzenie zameldowania i w punkcie sprzedaży zostanie utworzone zadanie. 

## <a name="additional-resources"></a>Dodatkowe zasoby

[Włączanie powiadomień zameldowania odbiorcy w punkcie sprzedaży](enable-customer-check-in.md)
