---
title: Tworzenie zamówień na podstawie cząstkowego kanału informacyjnego dla transakcji w sklepach sieci sprzedaży
description: Ten temat opisuje tworzenie zamówień na podstawie cząstkowego kanału informacyjnego dla transakcji w sklepach w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 10/14/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7d5812893edff24a60a0e2eb3607701ac47a8a78
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057177"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions-public-preview"></a>Tworzenie zamówień na podstawie cząstkowego kanału informacyjnego dla transakcji w sklepach sieci sprzedaży (publiczna wersja zapoznawcza)

[!include [banner](includes/banner.md)]

W wersji 10.0.4 lub wcześniejszej rozwiązania Dynamics 365 Retail księgowanie zestawień jest operacją na koniec dnia i wszystkie transakcje są księgowane w księgach na koniec dnia. Duże transakcje muszą być następnie przetworzone w ciągu krótkiego okresu, czasami powodując niepowodzenie ładowania, blokowania i księgowania zestawień. Sprzedawcy detaliczni nie mogą także rozpoznać przychodu i płatności w swoich księgach w ciągu dnia.

Dzięki publicznej wersji zapoznawczej tworzenia zamówień na podstawie cząstkowego kanału informacyjnego wprowadzonego w wersji 10.0.5 rozwiązania Retail transakcje są przetwarzane w ciągu dnia i dopiero na koniec dnia przetwarzane są uzgodnienia finansowe metod płatności oraz inne transakcje zarządzania gotówką. Funkcja ta rozkłada obciążenie pracą podczas tworzenia zamówień sprzedaży, faktur i płatności w ciągu dnia, oferując poprawioną wydajność i zdolność rozpoznania przychodu i płatności w księgach niemal w czasie rzeczywistym. 


## <a name="how-to-use-trickle-feed-based-posting"></a>Jak korzystać z księgowania na podstawie cząstkowego kanału informacyjnego
  
1. Aby włączyć księgowanie na podstawie cząstkowego kanału informacyjnego transakcji, przejdź do **Administrowanie systemem > Ustawienia > Konfiguracja licencji** i wyłącz klucz **Zestawienia**.

2. Na tej samej stronie włącz klucz licencji **Zestawienia (cząstkowy kanał informacyjny) — wersja zapoznawcza**. Podczas włączania tego klucza upewnij się, że brak oczekujących na zaksięgowanie zestawień. 

    > [!Important]
    > Przed włączeniem klucza licencji **Zestawienia (cząstkowy kanał informacyjny) — wersja zapoznawcza** upewnij się, że brak oczekujących na zaksięgowanie zestawień.

3. Bieżący dokument zestawienia będzie podzielony na dwa różne typy: zestawienie transakcyjne i sprawozdanie finansowe.

      - Zestawienie transakcyjne pobierze wszystkie niezaksięgowane i zweryfikowane transakcje i utworzy arkusze zamówień sprzedaży, faktur sprzedaży, płatności i rabatów oraz transakcje przychodu/wydatku według skonfigurowanej przez użytkownika częstotliwości. Proces ten powinien być skonfigurowany tak, by występować jak najczęściej, aby dokumenty były tworzone, gdy transakcje są przesyłane do centrali za pomocą zadania ściągania. Gdy zestawienie transakcyjne od razu tworzy zamówienia sprzedaży i faktury sprzedaży, nie ma potrzeby konfiguracji zadań wsadowych **Zaksięguj magazyn**. Jednakże ciągle można użyć ich do spełnienia konkretnych wymagań biznesowych użytkownika.  
      
     - Sprawozdanie finansowe będzie tworzone na koniec dnia i obsługuje tylko metodę zamknięcia **Zmiana**. To sprawozdanie będzie ograniczone do uzgodnienia finansowego i będzie tylko tworzyć arkusze dla różnic w kwotach między kwotą zliczoną i kwotą transakcji dla różnych metod płatności wraz z arkuszami dla innych transakcji zarządzania gotówką.   

4. Aby obliczyć zestawienie transakcyjne, kliknij **Retail i Commerce > Retail i Commerce — składniki IT > Księgowanie w punkcie sprzedaży > Oblicz zestawienia transakcyjne w partii**. Aby zaksięgować zestawienia zestawień transakcyjnych w partii, kliknij **Retail i Commerce > Retail i Commerce — składniki IT > Księgowanie w punkcie sprzedaży > Księguj zestawienia transakcyjne w partii**.

5. Aby obliczyć zestawienie finansowe, kliknij **Retail i Commerce > Retail i Commerce — składniki IT > Księgowanie w punkcie sprzedaży > Oblicz zestawienia finansowe w partii**. Aby zaksięgować zestawienia finansowe w partii, kliknij **Retail i Commerce > Retail i Commerce — składniki IT > Księgowanie w punkcie sprzedaży > Zaksięguj zestawienia finansowe w partii**.

> [!NOTE]
> Elementy menu **Retail i Commerce > Retail i Commerce — składniki IT > Księgowanie w punkcie sprzedaży > Oblicz zestawienia w partii** i **Retail i Commerce > Retail i Commerce — składniki IT > Księgowanie w punkcie sprzedaży > Księguj zestawienia w partii** zostały w tej nowej funkcji usunięte.

Typy zestawień transakcyjnych i sprawozdań finansowych mogą też być tworzone ręcznie. Przejdź do **Retail i Commerce > Kanały > Sklepy** i kliknij pozycję **Zestawienia**. Kliknij **Nowe**, a następnie wybierz typ zestawienia, które chcesz utworzyć. Pola na stronie **Zestawienia** i akcje pod **Grupa zestawień** strony wyświetlą odpowiednie dane i akcje na podstawie wybranego typu zestawienia.
