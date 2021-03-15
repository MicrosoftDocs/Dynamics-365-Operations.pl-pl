---
title: Ustawienia języka użytkownika i aplikacji POS
description: W tym temacie opisano, jak zmienić ustawienia języka w programach Modern POS (MPOS) i Cloud POS.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 0f196b3077b0a8d80cac93a8b6b3f8c5c08c3c96
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000567"
---
# <a name="point-of-sale-pos-application-and-user-language-settings"></a>Ustawienia języka użytkownika i aplikacji POS

[!include [banner](includes/banner.md)]

W tym temacie opisano, jak zmienić ustawienia języka w programach Modern POS (MPOS) i Cloud POS.

## <a name="overview"></a>Omówienie
Programy Modern POS (MPOS) i Cloud POS obsługują środowiska, w których ustawienia językowe i tłumaczenia mogą się różnić w zależności od sklepu i ustawień użytkownika. Na przykład sklep może znajdować się regionie, w którym głównym językiem odbiorców jest angielski, ale niektórzy pracownicy wolą korzystać z aplikacji w języku francuskim.

## <a name="data-language"></a>Język danych

Niezależnie od ustawień programy MPOS i Cloud POS zawsze używają ustawień języka sklepu do tłumaczenia danych. To zapewnia spójność środowiska dla wszystkich użytkowników i odbiorców. Przykładowe dane:

- Produkty
- Atrybuty i wartości
- Nazwy kategorii
- Drukowane lub wysyłane e-mailem potwierdzenia transakcji
- Nazwy metod płatności
- Komunikaty wyświetlacza wierszowego

Język sklepu będzie również używany na głównym ekranie logowania w punkcie sprzedaży, ponieważ przed zalogowaniem użytkownik nie jest znany. Jeśli tłumaczenie nie jest dostępne w języku sklepu, będzie używany język firmy.

### <a name="configuring-the-stores-language-setting"></a>Konfigurowanie ustawień języka dla sklepu

Język sklepu ustawia się w obszarze **Wszystkie sklepy** na stronie **Sklep** w menu **Ogólne &gt; Ustawienia regionalne &gt; Język**. Wybierz język dla każdego sklepu z listy rozwijanej.

## <a name="user-interface-language"></a>Język interfejsu użytkownika

Ustawienie języka użytkownika punktu sprzedaży określa tłumaczenia używane w interfejsie użytkownika aplikacji. Obejmuje to wszystkie etykiety, menu i listy, które nie są danymi. Jedynym wyjątkiem jest tekst wyświetlany na siatce przycisków punktu sprzedaży. Dla siatek przycisków nie są dostępne tłumaczenia, więc będą one zawsze wyświetlane zgodnie z konfiguracją przycisku. Aby włączyć tłumaczenia przycisków, trzeba skopiować i zachować siatki przycisków i przypisać je do użytkowników według potrzeb.

### <a name="configuring-the-users-language-setting"></a>Konfigurowanie ustawień języka użytkownika

Język użytkownika punktu sprzedaży ustawia się w obszarze **Wszyscy pracownicy** na stronie **Pracownik** w menu **Handel detaliczny i inny &gt; Język**. Nie da się go ustawić na karcie Profil. To ustawienie jest używane w punkcie sprzedaży. Jeśli nie ustawiono języka użytkownika lub tłumaczenia w wybranym języku są niedostępne, ustawienia językowe w punkcie sprzedaży wrócą do języka sklepu.

|             | Język interfejsu użytkownika                  | Język danych (produkty, formaty paragonów, wyświetlacz wierszowy itp.) |
|-------------|----------------------------|---------------------------------------------------------------|
| **Firma** | Domyślna                    | Domyślna                                                       |
| **Sklep**   | Zastępuje ustawienie dla firmy          | Zastępuje ustawienie dla firmy                                             |
| **Użytkownik**    | Zastępuje ustawienie dla sklepu lub firmy | Nigdy                                                         |


[!INCLUDE[footer-include](../includes/footer-banner.md)]