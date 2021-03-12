---
title: Definiowanie i obsługa kanałów sprzedaży detalicznej
description: Ten artykuł zawiera omówienie procesu konfigurowania sklepów tradycyjnych (fizycznych), określanych jako „sklepy” w Dynamics 365 Commerce. Znajdują się tu informacje o zadaniach, które należy wykonać przed i po skonfigurowaniu sklepu.
author: mugunthanm
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreTableListPagePreviewPane
audience: Application User
ms.reviewer: josaw
ms.custom: 16481
ms.assetid: 14496d96-1c72-43ce-a2e7-8467bab4ae46
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 51524ad6918d962d70a8a700f135f96e236f7d34
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000882"
---
# <a name="define-and-maintain-retail-channels"></a>Definiowanie i obsługa kanałów sprzedaży detalicznej

[!include [banner](includes/banner.md)]

Ten artykuł zawiera omówienie procesu konfigurowania sklepów tradycyjnych (fizycznych), określanych jako „sklepy” w Dynamics 365 Commerce. Znajdują się tu informacje o zadaniach, które należy wykonać przed i po skonfigurowaniu sklepu.

Commerce obsługuje wiele kanałów, takich jak sklepy internetowe, sklepy tradycyjne i biura obsługi. Sklep tradycyjny jest nazywany sklepem. Każdy sklep ma własne metody płatności, grupy cenowe, kasy punktów sprzedaży, konta przychodów i wydatków oraz personel. Wszystkie te elementy sklepu należy skonfigurować przed jego utworzeniem. Po utworzeniu sklepu, można przypisać produkty, które mają trafić do sklepu. Rejestry, pracowników i odbiorców również można przypisać do sklepu. Na koniec należy dodać nowy sklep do hierarchii organizacyjnej.

## <a name="setting-up-stores"></a>Konfigurowanie sklepów

Przed skonfigurowaniem sklepu w Commerce należy wykonać niektóre zadania wymagań wstępnych. Następnie można utworzyć sklep i dodać szczegóły.

### <a name="prerequisites"></a>Wymagania wstępne

Przed skonfigurowaniem sklepu należy wykonać następujące zadania:

1. Konfigurowanie struktury organizacji i hierarchii organizacyjnych dla asortymentów sieci sprzedaży, uzupełnień i raportowania.
2. Konfigurowanie magazynu reprezentującego sklep.
3. Konfigurowanie sekwencji identyfikatorów dla sklepów, zestawień dotyczących sklepu i załączników do zestawień.
4. Konfigurowanie parametrów Commerce.
5. Konfigurowanie metod płatności, które akceptuje sklep.
6. Do przetwarzania transakcji karty kredytowej w kasach punktów sprzedaży (POS)można też skonfigurować usługi płatności.
7. Konfigurowanie grup podatków.
8. Konfigurowanie produktów. W ramach tego zadania należy także skonfigurować hierarchie produktów, asortymentów produktów i wariantów produktu.
9. Konfigurowanie grup cenowych produktów.
10. Ustawianie cen produktu. W ramach tego zadania można również ustawić korekty cen, rabaty i okresy rabatu.
11. Konfigurowanie członków personelu.

    > [!NOTE]
    > Należy również przypisać odpowiednie uprawnienia dla pracowników, tak aby mogli logować się i wykonywać zadania za pomocą systemu POS.

12. Konfigurowanie profilów POS, które mają zostać przypisane do danego sklepu. Konfigurowanie profilów obejmuje wiele zadań, takich jak konfigurowanie rejestrów, konfigurowanie profilów trybu offline i konfigurowanie profilów i formatów paragonu.

Przejrzyj wszystkie zadania zawarte w wymaganiach wstępnych i wykonaj tylko te, które odnoszą się do Ciebie.

### <a name="set-up-a-store"></a>Ustawianie sklepu

Po zakończeniu zadania wymagań wstępnych wykonaj te zadania, aby skonfigurować szczegóły sklepu:

1. Utworzyć sklep.
2. Przypisywanie grupy podatków do sklepu.
3. Przypisywanie akceptowanych metod płatności do sklepu.
4. Dodawanie szczegółów do opisów produktów dla produktów, które oferujesz w sklepach. Na przykład można dodawać obrazy i tekst sformatowany RTF. Te informacje szczegółowe o produkcie są wyświetlane w różnych kontekstach, takich jak kasy w punkcie sprzedaży lub wydrukowane etykiety.
5. Dodawanie sklepu sieci sprzedaży do domyślnej hierarchii organizacyjnej przypisanej do celu **Asortyment sieci sprzedaży**, **Uzupełnianie zapasów sieci sprzedaży** lub **Raportowanie sieci sprzedaży**.

### <a name="after-you-set-up-a-store"></a>Po skonfigurowaniu sklepu

Po wprowadzeniu szczegółów sklepu zakończ te zadania, aby wysłać nowe dane sklepu do POS:

1. Konfigurowanie kas w punkcie sprzedaży dla sklepu.
2. Dodawanie asortymentów produktów do sklepu.
3. Przetwarzanie asortymentów, aby wygenerować listę produktów, które są uwzględnione w asortymencie i aby udostępnić produkty w sklepie.
4. Wysyłanie danych, takich jak sekwencje numerów, profile sprzętu, układy ekranu punktu sprzedaży do kas POS.
5. Publikowanie sklepu, aby wysyłać dane sklepu do POS.
6. Uruchamianie zadań, aby wysyłać dane sklepu do POS.

## <a name="organization-hierarchies"></a>Hierarchie organizacyjne

Commerce używa hierarchii organizacji do tworzenia struktury w kanałach. Hierarchie organizacji reprezentują relacje między organizacjami, które składają się na działalność. Podczas konfigurowania sklepów, można je dodawać do hierarchii organizacyjnej. Sklepy współdzielą wówczas dane używane do asortymentów, uzupełnienia i raportów.

> [!NOTE]
> Aby korzystać z funkcji sprzedaży w aplikacji Commerce, klucz konfiguracji dla opcji **Wielokrotna wysyłka** musi być włączony. Ten klucz konfiguracji można znaleźć w kluczach **konfiguracji handlu** w obszarze **Administracja systemem**\> **Instalator** \> **Konfiguracja licencji**. Jest to wymagane z powodu różnych operacji weryfikacji na podstawie adresu dostawy skonfigurowanego na poziomie wiersza zamówienia sprzedaży.

