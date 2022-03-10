---
title: Tworzenie i fakturowanie międzyfirmowego zamówienia sprzedaży dla odbiorcy zewnętrznego
description: W tym temacie wyjaśniono, jak utworzyć i zafakturować międzyfirmowe zamówienie sprzedaży dla klienta zewnętrznego
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: b5f7342a997407c8701b836c2a6a6222d8512121
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075001"
---
# <a name="create-and-invoice-an-intercompany-sales-order-for-an-external-customer"></a>Tworzenie i fakturowanie międzyfirmowego zamówienia sprzedaży dla odbiorcy zewnętrznego

[!include [banner](../../includes/banner.md)]

Handlu międzyfirmowego można używać do rejestrowania sprzedaży produktu od jednej firmy do innej firmy, która znajduje się w tej samej organizacji.

W przypadku tworzenia oryginalnego zamówienia sprzedaży można automatycznie tworzyć międzyfirmowe zamówienie zakupu dla dostawcy międzyfirmowego. Powoduje to automatyczne utworzenie międzyfirmowego zamówienia sprzedaży w podmiocie prawnym dostawcy międzyfirmowego.

Na poniższej ilustracji przedstawiono przepływ transakcji podczas tworzenia zamówienia sprzedaży dla klienta zewnętrznego, ale przed dostarczeniem produktu do klienta produkt musi być zamówiony w innej firmie w organizacji. W takim przypadku międzyfirmowe zamówienie zakupu jest tworzone dla konta dostawcy, które reprezentuje inną firmę. Z kolei międzyfirmowe zamówienie sprzedaży jest tworzone w innej firmie dla konta odbiorcy, które reprezentuje Twoją firmę. Po zafakturowaniu międzyfirmowego zamówienia zakupu faktura za oryginalne zamówienie sprzedaży jest księgowana automatycznie, jeśli jest to dostawa bezpośrednia.

![Międzyfirmowy proces sprzedaży zewnętrznej](media/intercompanyexternalsalesprocess.png)

W przypadku korzystania z dostawy bezpośredniej i wybrania opcji **Dokument dostawy** w polu **Ilość** formularza **Księgowanie faktury**, faktura międzyfirmowego dostawcy zostanie utworzona na podstawie wcześniej zaksięgowanego międzyfirmowego dokumentu przyjęcia produktów.

## <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem, upewnij się, że spełniono następujące wymagania wstępne, aby automatycznie zaksięgować i wydrukować faktury międzyfirmowe.

1. Przejdź do pozycji **Sprzedaż i marketing \> Odbiorcy \> Wszyscy odbiorcy**.
1. W okienku akcji na karcie **Ogólne** wybierz opcję **Międzyfirmowe**.
1. Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Dostawcy \> Wszyscy dostawcy**.
1. W okienku akcji na karcie **Ogólne** wybierz opcję **Międzyfirmowe**.
1. Na stronie **międzyfirmowej** dotyczącej dostawcy lub odbiorcy w obszarze **Zasady zamówienia zakupu** w grupie pól **Międzyfirmowe zamówienie zakupu (dostawa bezpośrednia)** zaznacz pole wyboru **Automatycznie księguj fakturę**.
1. W obszarze **Zasady zamówienia zakupu** w grupie pól **Oryginalne zamówienie sprzedaży (dostawa bezpośrednia)** zaznacz pole wyboru **Automatycznie księguj fakturę**. Zaznacz to pole wyboru, jeśli chcesz, aby faktura za oryginalne zamówienie sprzedaży była automatycznie drukowana po zaksięgowaniu faktury dostawcy międzyfirmowego.

> [!NOTE]
> Ustawienia drukowania faktury są określone przez konfigurację modułu, dokumentu lub transakcji na stronie **Konfiguracja zarządzania drukowaniem**.

## <a name="create-an-original-sales-order-for-an-external-customer"></a>Tworzenie oryginalnego zamówienia sprzedaży dla odbiorcy zewnętrznego

Wykonaj poniższe kroki w firmie A. Ta procedura odnosi się do pola o nazwie 1 na rysunku.

1. Przejdź do pozycji **Rozrachunki z odbiorcami \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Na stronie listy **Wszystkie zamówienia sprzedaży** utwórz oryginalne zamówienie sprzedaży.. Wartości pól są kopiowane z konta odbiorcy do zamówienia sprzedaży.
1. Na stronie **Zamówienie sprzedaży** wybierz **Widok nagłówka** w okienku akcji.
1. Na skróconej karcie **Ustawienia międzyfirmowe** zaznacz pole wyboru **Automatyczne zamówienia międzyfirmowe**.
1. Aby dostawca międzyfirmowy dostarczał towar bezpośrednio do odbiorcy zewnętrznego, zaznacz pole wyboru **Bezpośrednia dostawa**.
1. Po zakończeniu wprowadzania zamówienia sprzedaży zamknij stronę **Zamówienie sprzedaży**.

Międzyfirmowe zamówienie zakupu jest tworzone automatycznie dla wszystkich towarów, które mają przypisanego dostawcę międzyfirmowego, a następnie tworzone jest międzyfirmowe zamówienie sprzedaży. Komunikat informacyjny informuje, że utworzono międzyfirmowe zamówienie zakupu i międzyfirmowe zamówienie sprzedaży. Komunikat zawiera także łącza do tych zamówień. Jeśli nie znaleziono towaru, wyświetlane jest czerwone ostrzeżenie, które oznacza, że proces tworzenia zamówienia nie został zakończony.

> [!NOTE]
> Jeśli tworzysz kilka zamówień w różnych firmach, a pozycje nie zostały znalezione w jednej z firm, proces tworzenia zamówienia zostanie zatrzymany, nawet dla firm, które mogłyby realizować swoje zamówienia.

## <a name="invoice-an-intercompany-sales-order"></a>Fakturowanie międzyfirmowego zamówienia sprzedaży

Po zafakturowaniu międzyfirmowego zamówienia sprzedaży odpowiednie międzyfirmowe zamówienie zakupu jest fakturowane automatycznie. Następnie, jeśli oryginalne zamówienie sprzedaży jest zamówieniem dostawy bezpośredniej, oryginalne zamówienie sprzedaży jest automatycznie fakturowane.

Wykonaj te czynności w osobie prawnej B. Ta procedura odpowiada polu oznaczonemu 2 na ilustracji.

1. Przejdź do pozycji **Rozrachunki z odbiorcami \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Wróć do strony **Wszystkie zamówienia sprzedaży** i wybierz międzyfirmowe zamówienie sprzedaży.
1. W okienku akcji wybierz kartę **Faktura**, a następnie ponownie wybierz opcję **Faktura**.
1. Zaznacz pole wyboru **Księgowanie**.
1. Wybierz zamówienie sprzedaży, a następnie wybierz **OK**.

Następnie automatycznie tworzona jest faktura sprzedawcy dla tego zamówienia i księgowana w firmie A. Jeśli pierwotne zamówienie sprzedaży jest skonfigurowane jako dostawa bezpośrednia, faktura klienta jest tworzona dla pierwotnego zamówienia sprzedaży w firmie A.

> [!NOTE]
> Poprzednio, w przypadku scenariuszy sprzedaży między firmami, jeśli przepływ faktur dla dostawców był skonfigurowany w firmie dokonującej zakupów między firmami, zamówienie sprzedaży między firmami nie mogło zostać pomyślnie zafakturowane. W związku z tym przepływ faktur od dostawców musiał zostać wyłączony dla międzyzakładowej spółki zakupowej. 
> 
> To ograniczenie zostało naprawione dzięki funkcji wprowadzonej niedawno w wydaniu 10.0.25. Międzyzakładowe zamówienia sprzedaży mogą być teraz fakturowane, gdy w międzyzakładowej firmie zakupowej skonfigurowany jest przepływ pracy z fakturą dla sprzedawcy.
> 
> Aby włączyć tę funkcję, wykonaj wymienione poniżej kroki.
>
> 1. Wybierz podmiot prawny sprzedaży wewnątrz firmy.  
> 2. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy**.
> 3. Wybierz klienta dla międzyzakładowej spółki handlowej.
> 4. Przejdź do **Ogólne \>Konfiguracja \> Międzyfirmowa**.
> 5. W zakładce **Polityka zamówień publicznych** zaznacz parametr **Omijaj obieg faktur dostawcy dla faktur wystawianych przez dostawców wewnętrznych**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
