---
title: Tworzenie składników majątku na podstawie zamówień zakupu
description: W tym artykule wyjaśniono, w jaki sposób można utworzyć listę pozycji składników majątku, które mogą służyć jako podstawa do tworzenia składników majątku dla zadań konserwacyjnych w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectItem, EntAssetPendingAssets
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8bee66e2d35af6daa8d86539e52b558bde3c79a1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893708"
---
# <a name="create-assets-based-on-purchase-orders"></a>Tworzenie składników majątku na podstawie zamówień zakupu

[!include [banner](../../includes/banner.md)]

 

W tym artykule wyjaśniono, w jaki sposób można utworzyć listę pozycji składników majątku, które mogą służyć jako podstawa do tworzenia składników majątku dla zadań konserwacyjnych w module Zarządzanie składnikami majątku. Na podstawie pozycji składników majątku można wyświetlić listę wierszy zamówienia zakupu, które zostały utworzone dla tych pozycji. Celem tej funkcji jest łatwe tworzenie składnika majątku w module Zarządzanie składnikami majątku na podstawie zamówienia zakupu.

Najpierw należy skonfigurować pozycje, które mają być używane do tworzenia składników majątku z zamówienia zakupu w obszarze **Pozycje składnika majątku**. Po utworzeniu wiersza zamówienia zakupu należy utworzyć składniki majątku w obszarze **Oczekujące składniki majątku**. Można zdecydować, na którym etapie zamówienia zakupu ma zostać utworzony składnik majątku.


## <a name="select-asset-items"></a>Wybieranie pozycji składnika majątku

1. Kliknij **Zarządzanie składnikami majątku** > **Ustawienia** > **Składniki majątku** > **Pozycje**.
2. Kliknij przycisk **Nowy**, aby utworzyć nową pozycję składnika majątku.
3. Wybierz pozycję w polu **Kod pozycji**. Po opuszczeniu tego pola nazwa pozycji jest automatycznie wstawiana w polu **Nazwa produktu**.
4. Na karcie skróconej **Ogólne** wybierz typ składnika majątku dla pozycji.
5. Wybierz producenta i model składnika majątku dla pozycji.
6. Zapisz pozycję.


## <a name="create-assets-from-pending-assets"></a>Tworzenie składników majątku z oczekujących pozycji

1. Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Składniki majątku** > **Oczekujące składniki majątku**.
2. Zostanie wyświetlona zaktualizowana lista zamówień zakupu na podstawie pozycji wybranych w obszarze **Pozycje składników majątku**.
3. Można filtrować stany zamówień zakupu w celu wybrania stanu cyklu życia, w którym ma zostać utworzony składnik majątku. Na przykład czasami trzeba utworzyć składnik majątku tylko w kontekście zaksięgowania przyjęcia produktu na zamówieniu zakupu.
4. Wybierz link **Numer odwołania** w wierszu zamówienia zakupu, aby wyświetlić szczegółowe informacje na temat pozycji.
5. Jeśli chcesz edytować wymiary, które mają być wyświetlane na skróconej karcie **Wymiary magazynowe**, kliknij przycisk **Wyświetl wymiary** i wybierz odpowiednie opcje.
6. Jeśli składnik majątku ma zostać utworzony na podstawie wiersza zamówienia zakupu, zaznacz pole wyboru w kolumnie **Zaznacz** dla tego wiersza na stronie listy i kliknij przycisk **Utwórz składniki majątku** Zostanie wyświetlony komunikat z informacją o identyfikatorze składnika majątku.
7. Wybierz składnik majątku na liście **Wszystkie składniki majątku** i kliknij przycisk **Edytuj**, aby dodać więcej informacji do składnika majątku.
8. W obszarze **Oczekujących składniki majątku**, jeśli chcesz usunąć wiersz, ponieważ nie chcesz tworzyć składnika majątku, zaznacz pole wyboru w kolumnie **Oznacz** dla tego wiersza i kliknij przycisk **Odrzuć oczekujące składniki majątku**. Zostanie wyświetlony komunikat z informacją o identyfikatorze składnika majątku. Nie usuwasz zamówienia zakupu ani zamówienia sprzedaży, tylko rekord, z którego utworzono składnik majątku w module **Zarządzanie składnikami majątku**.

>[!NOTE]
>Wszystkie wymiary produktu (rozmiar, kolor, konfiguracja itp.) są automatycznie przenoszone do atrybutów składnika majątku. Wymiary śledzenia (numer seryjny) są zapisywane bezpośrednio w składniku majątku w chwili jego utworzenia.


## <a name="find-pending-assets"></a>Znajdowanie oczekujących składników majątku

Można uruchomić zadanie **Liczba oczekujących składników majątku**, aby sprawdzić oczekujące składniki majątku. Na przykład funkcja ta może być używana do odbierania powiadomień za każdym razem, gdy oczekujący składnik majątku jest gotowy do utworzenia jako składnik majątku.

1. Kliknij **Zarządzanie składnikami majątku** > **Okresowe** > **Składniki majątku** > **Liczba oczekujących składników majątku**.
2. Kliknij przycisk **OK**, aby uruchomić zadanie i zaktualizować listę w obszarze **oczekujące składniki majątku**.
3. To zadanie można skonfigurować tak, aby było uruchamiane jako zadanie wsadowe, na przykład raz dziennie.

**Uwaga:** Jeśli dane w zamówieniu zakupu zostały zmienione *po* utworzeniu składnika majątku na podstawie odpowiedniej pozycji, zmiany te nie zostaną odzwierciedlone w składniku majątku.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]