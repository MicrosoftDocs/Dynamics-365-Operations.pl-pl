---
title: Konfigurowanie zmiany alokacji pozycji na potrzeby pobierania w niedomiarze
description: Ten temat pokazuje, jak umożliwić pracownikom magazynu szybkie znajdowanie alternatywnych lokalizacji, jeżeli nie ma wystarczających zapasów w lokalizacji, do której zostali skierowani.
author: ShylaThompson
manager: tfehr
ms.date: 06/29/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e14a4fc72d256bea31296bff80d5b5818b95ea9d
ms.sourcegitcommit: ce397c2759f642c595e30fef58a770b50360b2bd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2020
ms.locfileid: "3527426"
---
# <a name="set-up-short-picking-item-reallocation"></a>Konfigurowanie zmiany alokacji pozycji na potrzeby pobierania w niedomiarze

[!include [banner](../../includes/banner.md)]

Ta procedura pokazuje, jak umożliwić pracownikom magazynu szybkie znajdowanie alternatywnych lokalizacji, jeżeli nie ma wystarczających zapasów w lokalizacji, do której zostali skierowani. 

Proces zmiany alokacji jest kontrolowany przez **Wyjątek pracy** i używany przez **Pracownika** magazynu.

Możliwe jest użycie zarówno automatycznego, ręcznego, jak i obu procesów zmiany alokacji:

- Automatyczna zmiana alokacji – dyrektywy lokalizacji służą do określenia, czy towary są dostępne w innej lokalizacji. Jeśli to możliwe, praca zostanie zaktualizowana, a użytkownik magazynu zostanie skierowany do lokalizacji alternatywnej.
- Ręczna zmiana pozycji – umożliwia użytkownikowi systemu magazynowego wybranie jednej lub wielu lokalizacji z niezarezerwowanymi ilościami towarów. 
- Automatycznie i ręcznie – Jeśli system nie jest w stanie wykonać automatycznej zmiany alokacji, a są dostępne lokalizacje z niezarezerwowanymi ilościami, użytkownik będzie monitowany o wybranie lokalizacji.

## <a name="set-up-work-exceptions"></a>Ustaw wyjątki pracy
Istnieje możliwość zdefiniowania kilku wyjątków dotyczących pracy z różnymi zasadami zmiany alokacji towarów, aby umożliwić pracownikowi magazynu wybór towaru na podstawie potrzeb przesyłki, którą akurat przetwarza.

Do stworzenia tej procedury wykorzystano dane z firmy demonstracyjnej USMF.

1. W **okienku nawigacji** przejdź do **Zarządzanie magazynem > Ustawienia > Praca > Wyjątki dotyczące pracy**.
2. Kliknij przycisk **Nowy** 
3. W polu **Kod wyjątku pracy** wpisz wartość. Będzie to tytuł tego wyjątku. Na przykład: Ręczne pobieranie w niedomiarze.
4. W polu **Opis** wpisz wartość. Będzie to krótki opis wykorzystania tego wyjątku. Na przykład, Pobranie w niedomiarze – pozycja niedostępna.
5. W polu **Typ wyjątku** zaznacz wartość „**Pobranie w niedomiarze**”.
6. Zaznacz pole wyboru **Korekta zapasów**. Jeśli została wybrana, ta opcja oznacza, że zapasy będą automatycznie korygowane na 0 w lokalizacji pobierania w niedomiarze.
7. W polu **Kod domyślnego typu korekty** wprowadź lub wybierz wartość. Na przykład w USMF można wybrać opcję **Usuń Res Adj Out**. Każdy kod typu korekty zawiera cztery cechy: nazwa, opis, nazwa arkusza magazynowego i **Usuń rezerwacje**. Jeśli opcja **Usuń rezerwacje** jest włączona, rezerwacje wiersza zamówienia z pobrania w niedomiarze zostanie usunięte.  
8. W polu **Zmiana pozycji przedmiotów** wybierz wartość, np. „Ręcznie”. Jeśli wybierzesz opcję Ręcznie lub Automatyczne i ręczne, pracownikowi magazynu trzeba włączyć funkcję stosowania ręcznej zmiany alokacji.

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a>Konfigurowanie pracownika do używania ręcznej zmiany alokacji

Do stworzenia tej procedury wykorzystano dane z firmy demonstracyjnej USMF.

1. Zamknij stronę.
2. W **okienku nawigacji** przejdź do **Zarządzanie magazynem > Ustawienia > Pracownik**.
3. Kliknij przycisk **Edytuj**.
4. Na liście zaznacz pracownika. Na przykład Julia Funderburk.
5. Rozwiń skróconą kartę **Użytkownicy**.
6. Na liście wybierz **Identyfikator użytkownika**. Na przykład 24.
7. Rozwiń skróconą kartę **Praca**.
8. W polu **Zezwalaj na ręczną zmianę alokacji pozycji** wybierz opcję **Tak**.
