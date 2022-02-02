---
title: Tworzenie zamówień na podstawie cząstkowego kanału informacyjnego dla transakcji w sklepach sieci sprzedaży
description: Ten temat opisuje tworzenie zamówień na podstawie cząstkowego kanału informacyjnego dla transakcji w sklepach w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 01/11/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 67b66cd4bf2a77f3ab7f33f691156e38cc13770a
ms.sourcegitcommit: 27475081f3d2d96cf655b6afdc97be9fb719c04d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/12/2022
ms.locfileid: "7964636"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions"></a>Tworzenie zamówień na podstawie cząstkowego kanału informacyjnego dla transakcji w sklepach sieci sprzedaży

[!include [banner](includes/banner.md)]

W wersji 10.0.5 i późniejszych rozwiązania Microsoft Dynamics 365 Commerce zaleca się przejście ze wszystkimi procesami księgowania zestawień do procesów księgowania na podstawie cząstkowego kanału informacyjnego. Używanie funkcji księgowania na podstawie cząstkowego kanału informacyjnego niesie za sobą znaczne korzyści biznesowe i związane z wydajnością. Transakcje sprzedaży są przetwarzane w ciągu dnia. Transakcje gotówkowe i przy użyciu środków płatniczych są przetwarzane w ramach sprawozdania finansowego na koniec dnia. Funkcja księgowania na podstawie cząstkowego kanału informacyjnego umożliwia ciągłe przetwarzanie zamówień sprzedaży, faktur i płatności. Dzięki temu zapasy, przychody i płatności są aktualizowane i rozpoznawane niemalże w czasie rzeczywistym.

## <a name="use-trickle-feed-based-posting"></a>Użyj księgowania na podstawie cząstkowego kanału informacyjnego

> [!IMPORTANT]
> Przed włączeniem księgowania na podstawie cząstkowego kanału informacyjnego należy upewnić się, że nie istnieją obliczone ani niezaksięgowane zestawienia. Przed włączeniem tej funkcji zaksięguj wszystkie zestawienia. Otwarte zestawienia można sprawdzić w obszarze roboczym **Finanse sklepu**.

Aby włączyć księgowanie na podstawie cząstkowego kanału informacyjnego transakcji sieci sprzedaży, włącz funkcję o nazwie **Zestawienia sieci sprzedaży — cząstkowy kanał informacyjny** w obszarze roboczym **Zarządzanie funkcjami**. Zestawienia będą dzielić się na dwa różne typy: zestawienia transakcyjne i sprawozdania finansowe.

### <a name="transactional-statements"></a>Zestawienia transakcyjne

Proces przetwarzania zestawień transakcyjnych powinien być uruchamiany często w ciągu dnia, aby dokumenty były tworzone, gdy transakcje są przesyłane do centrali Commerce. Transakcje są ładowane ze sklepów do centrali Commerce po uruchomieniu **zadania ściągania**. Należy również uruchomić zadanie **Sprawdź poprawność transakcji w sklepie**, aby sprawdzić poprawność transakcji, tak aby transakcje zostały pobrane do zestawienia transakcyjnego.

Zaplanuj częste uruchamianie następujących zadań:

- Aby obliczyć zestawienie transakcyjne, uruchom zadanie **Oblicz zestawienia transakcyjne w partii** (**Retail i Commerce \> Retail i Commerce — składniki IT \> Księgowanie w punkcie sprzedaży \> Oblicz zestawienia transakcyjne w partii**). Uruchomienie tego zadania spowoduje odbiór wszystkich niezaksięgowanych i zweryfikowanych transakcji i dodanie ich do nowego zestawienia transakcyjnego.
- Aby zaksięgować zestawienie transakcyjne w partii, uruchom zadanie **Księguj zestawienia transakcyjne w partii** (**Retail i Commerce \> Retail i Commerce — składniki IT \> Księgowanie w punkcie sprzedaży \> Księguj zestawienia transakcyjne w partii**). To zadanie spowoduje uruchomienie procesu księgowania i utworzenie zamówień sprzedaży, faktur sprzedaży, arkuszy płatności, arkuszy rabatów oraz transakcji przychodów/wydatków dla niezaksięgowanych sprawozdań, które nie zawierają żadnych błędów. 

### <a name="financial-statements"></a>Sprawozdania finansowe

Przetwarzanie sprawozdania finansowego powinno stanowić proces przeprowadzany na koniec dnia. Ten typ przetwarzania sprawozdań obsługuje tylko metodę zamykania **Zmiana** i odbiera tylko zamknięte zmiany. Sprawozdania będą ograniczone do uzgodnienia finansowego. Będą tworzyć tylko arkusze dla różnic w kwotach między kwotą zliczoną i kwotą transakcji dla metod płatności i arkusze dla innych transakcji zarządzania gotówką.

Sprawozdania finansowe umożliwiają także przegląd następujących transakcji: transakcje deklaracji środków płatniczych, transakcje płatności, transakcje środków płatniczych wpłaconych na konto bankowe i bezpieczne transakcje środków płatniczych. Strona szczegółów środków płatniczych jest widoczna tylko po wybraniu sprawozdania finansowego.

![Obraz przedstawiający obszar szczegółów środków płatniczych w formularzu zaksięgowanych sprawozdań tylko po wybraniu sprawozdania finansowego.](./media/Trickle-feed-posted-statements-transaction-view.png)

Zaplanuj godziny rozpoczęcia i zakończenia następujących zadań sprawozdania finansowego na podstawie oczekiwanego końca dnia:

- Aby obliczyć sprawozdanie finansowe, uruchom zadanie **Oblicz sprawozdania finansowe w partii** (**Retail i Commerce \> Retail i Commerce — składniki IT \> Księgowanie w punkcie sprzedaży \> Oblicz sprawozdania finansowe w partii**). To zadanie spowoduje zebranie wszystkich niezaksięgowanych transakcji finansowych i dodanie ich do nowego sprawozdania finansowego.
- Aby zaksięgować sprawozdania finansowe w partii, uruchom zadanie **Księguj sprawozdania finansowe w partii** (**Retail i Commerce \> Retail i Commerce — składniki IT \> Księgowanie w punkcie sprzedaży \> Księguj sprawozdania finansowe w partii**).

### <a name="manually-create-statements"></a>Ręczne tworzenie sprawozdań

Istnieje także możliwość ręcznego tworzenia typów zestawień transakcyjnych i sprawozdań finansowych. 

1. Przejdź do **Retail i Commerce \> Kanały \> Sklepy** i kliknij pozycję **Zestawienia**. 
2. Wybierz opcję **Nowy**, a następnie wybierz typ zestawienia do utworzenia. Pola na stronie **Zestawienia** wyświetlą odpowiednie dane na podstawie wybranego typu zestawienia, a odpowiednie akcje są widoczne w obszarze **Grupa zestawień**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
