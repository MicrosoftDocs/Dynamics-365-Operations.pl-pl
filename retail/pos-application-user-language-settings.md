---
title: "Ustawienia języka użytkownika i aplikacji w punkcie sprzedaży"
description: "W tym temacie opisano jak zmienić ustawienia języka w Retail POS nowoczesnych (MPOS) i POS chmury."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: bf5b75572529bb497d3079752de187f30aa59294
ms.lasthandoff: 03/31/2017


---

# <a name="pos-application-and-user-language-settings"></a>Ustawienia języka użytkownika i aplikacji w punkcie sprzedaży

W tym temacie opisano jak zmienić ustawienia języka w Retail POS nowoczesnych (MPOS) i POS chmury.

<a name="overview"></a>Przegląd
========

Retail POS nowoczesnych (MPOS) i Cloud POS obsługują środowiskach, gdzie ustawienia języka i tłumaczenia mogą się różnić między ustawienia magazynu i użytkownika. Na przykład sklep może się w regionie, gdzie język angielski jest najczęściej dla swoich klientów, ale niektórzy pracownicy wolą używać aplikacji z tłumaczenia.

## <a name="data-language"></a>Język danych
Niezależnie od ustawień użytkownika, MPOS i chmury POS będzie zawsze sklepu języka ustawienia służą do określania tłumaczenia, stosowany do przetwarzania danych. Daje to pewność, że wszyscy użytkownicy i klienci mają spójny wygląd.  Przykłady takich danych to:

-   Produkty
-   Atrybuty i wartości
-   Nazwy kategorii
-   Drukowane lub wysyłane e-mailem potwierdzenia transakcji
-   Nazwy metod płatności
-   Komunikaty wyświetlacza wierszowego

Języka w sklepie będzie również dla głównego ekranu logowania POS, ponieważ użytkownik nie jest znana przed zalogowaniem. Jeśli tłumaczenie nie jest dostępne dla języka tego sklepu, punktu sprzedaży powróci do języka firmy.

### <a name="configuring-the-stores-language-setting"></a>Konfigurowanie ustawień języka dla sklepu

Ustawienie języka dla sklepu jest ustawiona z **wszystkich sklepów detalicznych** na **Retail Store** strony w obszarze ** Ogólne &gt;ustawienia regionalne &gt;języka. ** Użyj spadek w dół, aby wybrać języka dla każdego sklepu.

## <a name="user-interface-language"></a>Język interfejsu użytkownika
Ustawienie języka użytkownika POS określa tłumaczenia używany w interfejsie użytkownika aplikacji. Obejmuje to wszystkie etykiety, menu i list, które nie są uważane za dane. Jedynym wyjątkiem jest tekst, który jest wyświetlany na siatki przycisków punktu sprzedaży. Siatki przycisków nie obsługują tłumaczenia, więc zawsze pokażą tekst zgodnie z definicją na przycisku. W celu wsparcia przetłumaczonych przyciski, będziesz musiał kopiować i Obsługa siatek oddzielnych przycisków i przypisywać je do użytkowników stosownie do przypadku.

### <a name="configuring-the-users-language-setting"></a>Konfigurowanie ustawień języka użytkownika

Ustawienie języka użytkownika POS jest ustawiona z **wszystkich pracowników** na **pracownika** strony pod **Retail &gt;języka**.  Nie ustawiono na głównej karcie profilu.  To ustawienie nie jest używane przez organizacje producentów. Jeśli nie ustawiono języka użytkownika lub tłumaczenia w wybranym języku są niedostępne, ustawienia językowe w punkcie sprzedaży wrócą do języka sklepu.  

|             |                            |                                                                   |
|-------------|----------------------------|-------------------------------------------------------------------|
| ** **       | **Język interfejsu użytkownika** ** **      | **Język danych (produkty, formaty paragonów, wyświetlacz wierszowy itp.)** |
| **Firma** | Domyślna                    | Domyślna                                                           |
| **Sklep**   | Zastępuje ustawienie dla firmy          | Zastępuje ustawienie dla firmy                                                 |
| **User**    | Zastępuje ustawienie dla sklepu lub firmy | Nigdy                                                             |




