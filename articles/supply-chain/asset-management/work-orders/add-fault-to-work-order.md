---
title: Dodawanie błędu do zlecenia pracy
description: W tym temacie opisano sposób dodawania rejestracji błędów do zleceń pracy w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e82026f1d73e7368d93109bc0b895b7368ac84d4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435252"
---
# <a name="add-fault-to-work-order"></a>Dodawanie błędu do zlecenia pracy

[!include [banner](../../includes/banner.md)]



Do zlecenia pracy można dodawać usterki, które zostały skonfigurowane w projektancie usterek. Co najmniej jeden rekord usterki musi być połączony z typami składników majątku, które są używane dla składnika majątku wybranego w tym zleceniu pracy. Aby uzyskać więcej informacji o konfiguracji, zobacz temat [Zarządzanie usterkami](../setup-for-work-orders/fault-management.md).

1. Wybierz pozycję **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.

2. Wybierz zlecenie pracy, w którym chcesz przeprowadzić rejestrację usterek, a następnie w okienku akcji, na karcie **Zlecenie pracy**, w grupie **Składnik majątku** wybierz pozycję **Usterka składnika majątku**.

3. Na skróconej karcie **Objawy** wybierz pozycję **Dodaj wiersz**. Sekwencyjny numer usterki jest automatycznie wprowadzany w polu **Usterka**.

4. W polu **Objaw usterki** wybierz odpowiedni objaw.

5. W polach **Obszar usterki** i **Typ usterki** wybierz odpowiednie wartości.

6. W polu **Data usterki** zostanie automatycznie ustawiona bieżąca data. W razie potrzeby możesz wybrać inną datę.

7. Na skróconej karcie **Przyczyny dla wybranego objawu** dodaj wiersz w celu opisania przyczyny problemu.

8. Na skróconej karcie **Środki zaradcze dla wybranego objawu** dodaj wiersz, aby opisać możliwe rozwiązanie problemu.

9. Wybierz opcję **Zapisz**.

Na poniższej ilustracji pokazano przykład rejestracji usterki.

![Rysunek 1](media/19-work-orders.png)


## <a name="view-asset-faults"></a>Zobacz usterki składnika majątku

Na liście **Usterki składnika majątku** można uzyskać przegląd wszystkich usterek zarejestrowanych w składnikach majątku.

Na stronie listy **Usterki składnika majątku** można uzyskać przegląd wszystkich usterek, które zarejestrowano w składnikach majątku. Aby otworzyć stronę, wybierz pozycję **Zarządzanie składnikami majątku** > **Zapytania** > **Usterka składnika majątku** > **Usterki składnika majątku**.


## <a name="print-asset-fault-report"></a>Drukowanie raportu usterki składnika majątku

Na stronie z listą **Wszystkie składniki majątku** można wydrukować raport usterek składników majątku, który przedstawia wszystkie rejestracje usterek oraz graficzne omówienie statystyk dotyczących usterek.

1. Wybierz **Zarządzanie składnikami majątku** > **Wspólne** > **Składniki majątku** > **Wszystkie składniki majątku**.

2. Wybierz składnik majątku, dla którego ma zostać wydrukowany raport usterek.

3. W okienku akcji na karcie **Ogólne** w grupie **Raporty** wybierz pozycję **Usterka składnika majątku**.

4. Wprowadź konkretny okres lub wybierz typ usterki.

5. Wybierz przycisk **OK**, aby wydrukować raport.

>[!NOTE]
>Aby wydrukować raport usterek dla kilku składników majątku lub typów składników majątku, kliknij pozycję **Zarządzanie składnikami majątku** > **Raporty** > **Składniki majątku** > **Usterka składnika majątku**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]