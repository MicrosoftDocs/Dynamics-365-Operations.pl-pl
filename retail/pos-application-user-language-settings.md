---
title: "Ustawienia języka użytkownika i aplikacji w punkcie sprzedaży"
description: "W tym temacie opisano, jak zmienić ustawienia języka w programach Retail Modern POS (MPOS) i Cloud POS."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: b2cbdb8bc65a3bfa84620a50480c503c3bb07991
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="pos-application-and-user-language-settings"></a>Ustawienia języka użytkownika i aplikacji w punkcie sprzedaży

[!include[banner](includes/banner.md)]


W tym temacie opisano, jak zmienić ustawienia języka w programach Retail Modern POS (MPOS) i Cloud POS.

<a name="overview"></a>Przegląd
========

Programy Modern POS (MPOS) i Cloud POS obsługują środowiska, w których ustawienia językowe i tłumaczenia mogą się różnić w zależności od sklepu i ustawień użytkownika. Na przykład sklep może znajdować się regionie, w którym głównym językiem odbiorców jest angielski, ale niektórzy pracownicy wolą korzystać z aplikacji w języku francuskim.

## <a name="data-language"></a>Język danych
Niezależnie od ustawień programy MPOS i Cloud POS zawsze używają ustawień języka sklepu do tłumaczenia danych. To zapewnia spójność środowiska dla wszystkich użytkowników i odbiorców.  Przykładowe dane:

-   Produkty
-   Atrybuty i wartości
-   Nazwy kategorii
-   Drukowane lub wysyłane e-mailem potwierdzenia transakcji
-   Nazwy metod płatności
-   Komunikaty wyświetlacza wierszowego

Język sklepu będzie również używany na głównym ekranie logowania w punkcie sprzedaży, ponieważ przed zalogowaniem użytkownik nie jest znany. Jeśli tłumaczenie nie jest dostępne w języku sklepu, będzie używany język firmy.

### <a name="configuring-the-stores-language-setting"></a>Konfigurowanie ustawień języka dla sklepu

Język sklepu ustawia się w obszarze **Wszystkie sklepy sieci sprzedaży** na stronie **Sklep sieci sprzedaży”** w menu **Ogólne &gt; Ustawienia regionalne &gt; Język. **Wybierz język dla każdego sklepu z listy rozwijanej.

## <a name="user-interface-language"></a>Język interfejsu użytkownika
Ustawienie języka użytkownika punktu sprzedaży określa tłumaczenia używane w interfejsie użytkownika aplikacji. Obejmuje to wszystkie etykiety, menu i listy, które nie są danymi. Jedynym wyjątkiem jest tekst wyświetlany na siatce przycisków punktu sprzedaży. Dla siatek przycisków nie są dostępne tłumaczenia, więc będą one zawsze wyświetlane zgodnie z konfiguracją przycisku. Aby włączyć tłumaczenia przycisków, trzeba skopiować i zachować siatki przycisków i przypisać je do użytkowników według potrzeb.

### <a name="configuring-the-users-language-setting"></a>Konfigurowanie ustawień języka użytkownika

Język użytkownika punktu sprzedaży ustawia się w obszarze **Wszyscy pracownicy** na stronie **Pracownik** w menu **Handel detaliczny &gt; Język**.  Nie da się go ustawić na głównej karcie Profil.  To ustawienie jest używane przez aplikację punktu sprzedaży. Jeśli nie ustawiono języka użytkownika lub tłumaczenia w wybranym języku są niedostępne, ustawienia językowe w punkcie sprzedaży wrócą do języka sklepu.  

|             |                            |                                                                   |
|-------------|----------------------------|-------------------------------------------------------------------|
| ** **       | **Język interfejsu użytkownika** ** **      | **Język danych (produkty, formaty paragonów, wyświetlacz wierszowy itp.)** |
| **Firma** | Domyślna                    | Domyślna                                                           |
| **Sklep**   | Zastępuje ustawienie dla firmy          | Zastępuje ustawienie dla firmy                                                 |
| **Użytkownik**    | Zastępuje ustawienie dla sklepu lub firmy | Nigdy                                                             |






