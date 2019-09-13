---
title: Dodawanie błędu do zlecenia pracy
description: W tym temacie opisano sposób dodawania rejestracji błędów do zleceń pracy w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7c86973ca44d9113d14e180e27cc51343da5d2c0
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875845"
---
# <a name="add-fault-to-work-order"></a>Dodawanie błędu do zlecenia pracy

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Do zlecenia pracy można dodawać błędy ustawione w projektancie usterek. Składnik majątku wybrany w zleceniu pracy musi zawierać typy składników majątku, z którymi jest połączony jeden lub więcej rekordów usterek. Więcej informacji o ustawieniach można znaleźć w sekcji [Zarządzanie usterkami](../setup-for-work-orders/fault-management.md).

1. Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.

2. Z listy wybierz zlecenie pracy, dla którego chcesz dokonać rejestracji usterek i kliknij przycisk **Usterka składnika majątku**.

3. Na skróconej karcie **Objawy**, należy kliknąć przycisk **Dodaj wiersz**. Sekwencyjny numer błędu jest automatycznie wstawiany w polu **Usterka**.

4. Wybierz odpowiedni objaw w polu **Objaw usterki**.

5. Wybierz **Obszar usterki** i **Typ usterki**.

6. W polu **Data usterki** zostanie automatycznie ustawiona bieżąca data. W razie potrzeby można wybrać inną datę.

7. Na skróconej karcie **Przyczyny dla wybranego objawu** dodaj wiersz opisujący przyczynę problemu.

8. Na skróconej karcie **Środki zaradcze dla wybranego objawu** dodaj wiersz opisujący możliwe rozwiązanie problemu.

9. Kliknij przycisk **Zapisz**.

![Rysunek 1](media/19-work-orders.png)


## <a name="view-asset-faults"></a>Zobacz usterki składnika majątku

Na liście **Usterki składnika majątku** można uzyskać przegląd wszystkich usterek zarejestrowanych w składnikach majątku.

Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Usterka składnika majątku** > **Usterki składnika majątku**, aby otworzyć listę.


## <a name="print-asset-fault-report"></a>Drukowanie raportu usterki składnika majątku

Na stronie z listą **Wszystkie składniki majątku** można wydrukować raport dotyczący usterek składników majątku zawierający wszystkie rejestracje usterek oraz graficzne omówienie statystyk usterek.

1. Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Składniki majątku** > **Wszystkie składniki majątku**.

2. Na liście **Składniki majątku** wybierz składnik majątku, dla którego chcesz wydrukować raport usterki.

3. Na karcie **Ogólne** > **sekcja Raporty**, kliknij **Usterka składnika majątku**.

4. Wstaw konkretny okres lub wybierz typ błędu.

5. Kliknij przycisk **OK**, aby wydrukować raport.

>[!NOTE]
>Można również wydrukować raport o usterkach dla kilku składników majątku lub typów składników majątku klikając **Zarządzanie składnikami majątku** > **Raporty** > **Składniki majątku** > **Usterka składnika majątku**.

