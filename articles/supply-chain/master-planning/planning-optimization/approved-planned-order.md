---
title: Wyświetlanie zamówień planowanych, zarządzanie nimi i zatwierdzanie
description: Ten temat zawiera informacje dotyczące wyświetlania zamówień planowanych, zarządzania nimi i zatwierdzania ich w optymalizacji planowania.
author: ChristianRytt
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 3b9b5274481e693f9fa05eb084ec5505ce5bc2eb
ms.sourcegitcommit: 9283caad2d0636f98579c995784abec19fda2e3f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/22/2021
ms.locfileid: "5935664"
---
# <a name="view-manage-and-approve-planned-orders"></a>Wyświetlanie zamówień planowanych, zarządzanie nimi i zatwierdzanie

[!include [banner](../../includes/banner.md)]

Ten temat zawiera informacje dotyczące wyświetlania zamówień planowanych, zarządzania nimi i zatwierdzania ich w optymalizacji planowania.

## <a name="view-and-manage-planned-orders"></a><a name="view-planned-orders"></a>Wyświetlanie zamówień planowanych i zarządzanie nimi

Zamówienia planowane można wyświetlać na dowolnej stronie listy zamówień planowanych i zarządzać nimi. Przejdź do jednego z następujących miejsc, w zależności od typu zamówień planowanych, z którymi chcesz pracować:

- Planowanie główne \> Obszary robocze \> Planowanie główne
- Planowanie główne \> Planowanie główne \> Zamówienia planowane
- Kontrola produkcji \> Zlecenia produkcyjne \> Planowane zlecenie produkcyjne
- Zaopatrzenie i sourcing \> Zamówienia zakupu \> Planowane zamówienie zakupu
- Zarządzanie zapasami \> Zamówienia przychodzące \> Planowane przeniesienia
- Zarządzanie zapasami \> Zamówienia wychodzące \> Planowane przeniesienia

## <a name="view-and-edit-the-status-of-planned-orders"></a>Wyświetlanie i edytowanie stanu zamówień planowanych

Pole **Stan** każdego planowanego zamówienia umożliwia śledzenie postępu lub zmianę sposobu przetwarzania zamówienia planowanego. Dostępne są następujące wartości pola **Stan**:

- **Nieprzetworzone** — gdy planowane główne generuje zamówienia planowane, otrzymują one ten stan. Zamówienia planowane o tym stanie zostaną usunięte podczas następnego uruchomienia planowania.
- **Zakończone** — ten stan wskazuje, że zamówienie planowane zostało zakończone. Jeżeli nie chcesz ustalać zamówienia planowanego, możesz ręcznie zmienić jego stan na *Zakończone*. Należy zauważyć, że system traktuje stany *Nieprzetworzone* i *Zakończone* w taki sam sposób.
- **Zatwierdzone** — ten stan wskazuje, że zamówienie planowane jest zatwierdzone do ustalenia. Aby ustalić zamówienie planowane, można zmienić stan na *zatwierdzone*. Jeśli chcesz zachować zmiany wprowadzone w zamówieniu planowanym lub jeśli chcesz ustalić zamówienie planowane, zmień jego stan na *Zatwierdzone*. Zamówienia planowane o stanie *Zatwierdzone* są przez planowanie główne uznawane za ustalone i oczekujące na dostawę. W związku z tym nie są one modyfikowane ani usuwane podczas późniejszego planowania głównego. Aby osiągnąć to zachowanie, logika planowania kopiuje zamówienia planowane w stanie *Zatwierdzone* ze starej wersji planu do nowej wersji planu podczas planowania głównego. Należy zauważyć, że zamówienia planowane w stanie *Zatwierdzone* są uznawane za dostawę tylko w ramach określonego planu głównego.

Aby zmienić stan pojedynczego zamówienia planowanego, [otwórz stronę z listą zamówień planowanych](#view-planned-orders), otwórz zamówienie, a następnie wykonaj jedną z poniższych czynności:

- Na skróconej karcie **Ogólne** zmień wartość pola **Stan**.
- W okienku akcji, na karcie **Zamówienia planowane** w grupie **Proces** wybierz **Zmień stan**.
- Aby zaznaczyć zamówienie jako zatwierdzone, w okienku akcji wybierz opcję **Zatwierdź**.

Aby jednocześnie zmienić stan kilku planowanych zamówień, [otwórz stronę listy zamówień planowanych](#view-planned-orders), zaznacz pole wyboru obok każdego zamówienia, które chcesz zmienić, a następnie wykonaj jedną z poniższych czynności:

- W okienku akcji, na karcie **Zamówienia planowane** w grupie **Proces** wybierz **Zmień stan**.
- Aby zaznaczyć zamówienia jako zatwierdzone, w okienku akcji wybierz opcję **Zatwierdź**.

## <a name="approve-planned-orders"></a>Zatwierdzanie zamówień planowanych

Zatwierdzanie zamówień planowanych jest opcjonalnym krokiem w procesie tworzenia ustalonego zamówienia na podstawie zamówienia planowanego.

Na poniższej ilustracji pokazano, jak można używać wartości **Stan** przypisanej do każdego planowanego zamówienia w celu zaimplementowania przepływu pracy zatwierdzania. Aby wdrożyć proces zatwierdzania, ręcznie dostosuj wartość pola **Stan** dla każdego planowanego zamówienia, zgodnie z opisem w poprzedniej sekcji.

![Przepływ zamówienia planowanego](media/approved-planned-orders-1.png)

> [!TIP]
> Zaleca się zatwierdzanie zmodyfikowanych zamówień planowanych. W przeciwnym razie modyfikacje zostaną zignorowane i zastąpione podczas następnego planowania.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Zaakceptuj zamówienia planowane](planned-order-firming.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
