---
title: Konfigurowanie zasobów projektu
description: Ten temat zawiera informacje dotyczące konfigurowania lub występowania o zasoby projektu.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c882e23794e3937f85b3e73774b36deaf28ac3ed
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760638"
---
# <a name="set-up-project-resources"></a>Konfigurowanie zasobów projektu

[!include [banner](../includes/banner.md)]

Należy utworzyć kalendarz i skojarzyć go z pracownikiem. Kalendarz jest używany do planowania projektu i czasu pracy zasobów, które są zarezerwowane dla projektu. Podczas konfigurowania kalendarza kierownicy projektu wykonują bilansowanie zasobów jako część procesu optymalizacji zasobów. Na podstawie harmonogramu w kalendarzu można nakładać ograniczenia na zasoby. Kalendarz można zdefiniować na stronie **Kalendarze**.

Po skonfigurowaniu pracownika jako zasobu projektu można wybrać spośród pracowników, którzy pracują w firmie, dla której konfigurowane są zasoby. Można także wybrać pracowników z innych firm w organizacji. Ci pracownicy są określani jako zasoby międzyfirmowe.

W poniższych procedurach opisano, jak skonfigurować pracownika jako zasób projektu w swojej firmie i jak skonfigurować międzyfirmowy zasób projektu.

## <a name="set-up-a-worker-as-a-project-resource"></a>Konfigurowanie pracownika jako zasobu projektu

1. Na stronie **Pracownicy** na liście **Pracownicy** wybierz pracownika, którego chcesz dodać jako zasób projektu, i otwórz rekord tego pracownika.
2. W okienku akcji wybierz kolejno opcje **Projekt** &gt; **Ustawienia** &gt; **Ustawienia projektu**.
3. Wybierz kalendarz, a następnie zamknij stronę.

Można również określić domyślne projekty dla zasobu jako rodzaj wstępnego przypisania. Wstępnych przypisań można używać, gdy menedżer zasobów lub kierownik projektu wie z wyprzedzeniem, w których projektach zasób będzie pracował. Wstępne przypisania mogą być również oparte na wniosku inwestora projektu lub klienta. Aby wstępnie przypisać projekt, na stronie **Przypisz projekty** na karcie **Projekty** na liście **Pozostałe projekty** wybierz odpowiedni projekt.

## <a name="set-up-an-intercompany-resource"></a>Konfigurowanie zasobu międzyfirmowego

Podczas konfigurowania pracownika jako zasobu międzyfirmowego należy wypełnić pola konfiguracji w firmach wypożyczającej i pożyczającej.

### <a name="in-the-lending-company"></a>W firmie wypożyczającej

1. W usłudze Finance upewnij się, że firma wypożyczająca jest wybrana, a następnie wykonaj procedurę z poprzedniej sekcji „Konfigurowanie pracownika jako zasobu projektu”.
2. Na stronie **Księgowanie międzyfirmowe** wybierz opcję **Nowe**.
3. W polu **Identyfikator firmy** wybierz firmę wypożyczającą. Wypełnij pozostałe pola, a następnie wybierz przycisk **Zapisz**.
4. Na stronie **Cena transferowa** wybierz opcję **Nowa**.
5. W polu **Firma pożyczająca** wybierz odpowiednią firmę.
6. Aby wypożyczyć firmie pożyczającej tylko zasób utworzony na początku niniejszej sekcji, w polu **Zasób** zaznacz nazwę utworzonego zasobu. Aby udostępnić firmie pożyczającej wszystkie zasoby firmy wypożyczającej, zostaw pole **Zasób** puste.
7. Na stronie **Parametry modułu Zarządzanie projektami i ich księgowanie** na stronie **Międzyfirmowe** ustaw w polu **Włącz międzyfirmowe planowanie zasobów i kart czasu pracy** wartość **Tak**.

### <a name="in-the-borrowing-company"></a>W firmie pożyczającej

- Na stronie **Lista zasobów**, w filtrze wyszukiwania wprowadź nazwę zasobu, który został utworzony dla firmy wypożyczającej, aby sprawdzić, czy nazwa znajduje się na liście zasobów dla firmy pożyczającej.

## <a name="request-project-resources"></a>Wnioskowanie o zasoby projektu
Funkcja planowania zasobów projektu tylko pozwala menedżerom zasobów rozdzielać zasoby pracowników w projektach. Aby włączyć tę funkcję, należy wykonać następujące zadania lub upewnić się, że zostały one wykonane:

- Ustaw sekwencje numerów.
- Ustawianie przepływów pracy dla zarządzania projektami i ich księgowania.
- Włącz przepływy pracy żądań zasobów

Po wykonaniu poprzedniego zadania można wykonać następujące zadania według potrzeb:

- Tworzenie wniosku o zasób w odniesieniu do zasobu pracownika z rezerwacją wstępną.
- Monitorowanie wniosków o zasoby.
- Realizacja wniosków o zasoby.
- Wnioskowanie o zasób pracownika z SPP.
- Rezerwowanie zasobów do projektu bez wnioskowania o zasób pracownika.
