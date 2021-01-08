---
title: Automatyczne akceptowanie z optymalizacją planowania
description: W tym temacie opisano sposób korzystania z funkcji automatycznego ustalania z optymalizacją planowania.
author: ChristianRytt
manager: tfehr
ms.date: 11/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-30
ms.dyn365.ops.version: AX 10.0.7
ms.openlocfilehash: 61e9e6aa660bc0828645c6bf1f2655539804831a
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594533"
---
# <a name="autofirming-with-planning-optimization"></a>Automatyczne akceptowanie z optymalizacją planowania

[!include [banner](../../includes/banner.md)]

Funkcja automatycznego ustalania umożliwia nadawanie zamówień planowanych (zwolnienie) jako części procesu planowania głównego. Podczas ustalania zamówień planowanych są one przekształcane w rzeczywiste zamówienia zakupu, zamówienia przeniesienia lub zlecenia produkcyjne. Jeśli jest używana optymalizacja planowania, zamówienia planowane są ustalane podczas planowania głównego, gdy data zamówienia (czyli data rozpoczęcia) przypada w ramach horyzontu czasowego do ustalenia.

> [!NOTE]
> Aby możliwe było automatyczne ustalanie planowanego zamówienia zakupu, towar musi być skojarzony z dostawcą.

## <a name="turn-on-autofirming"></a>Włącz automatyczne akceptowanie

Aby włączyć automatyczne akceptowanie, należy wykonać następujące kroki.

1. W obszarze roboczym **Zarządzanie funkcjami** na liście na **nowej** karcie Wybierz opcję **Automatyczne ustalanie na potrzeby optymalizacji** planowania z listy. Jeśli funkcja nie jest wyświetlana na **nowej** karcie, sprawdź, czy **nie jest włączona** i **wszystkie** karty.
1. Wybierz **Włącz teraz**. Możesz też wybrać **harmonogram**, a następnie wybrać czas, w którym funkcja ma być włączona

## <a name="set-up-the-firming-time-fence"></a>Ustal horyzont czasowy akceptacji

Ten horyzont czasowy akceptowania jest obliczany od daty planowanego uruchomienia. Jest definiowane liczbą dni, która została wpisana. Horyzont czasowy ustalania można kontrolować w następujący sposób:

- Aby zdefiniować domyślny horyzont czasowy ustalania dla grupy zapotrzebowania, należy przejść do grup **Planowanie główne** \> **Ustawienia** \> **Zapotrzebowanie** \> **Grupy zapotrzebowania** i wybrać grupę zapotrzebowania. Następnie, na skróconej karcie w **Inne**, w polu **automatyczny horyzont czasowy akceptacji (dni)** wprowadź liczbę dni.
- Aby zastąpić horyzont czasowy ustalania, który jest zdefiniowany dla grupy zapotrzebowania dla określonej pozycji, przejdź do zwolnionych produktów w module **Zarządzanie informacjami o produktach** \> **Zwolnione produkty**, następnie w okienku akcji wybierz pozycję **Plan**, a następnie wybierz pozycję **Zapotrzebowanie na pozycję**. Następnie na karcie **Ogólne** wybierz opcję **Zastąp horyzont czasowy**, a następnie w polu **automatyczny horyzont czasowy akceptacji (dni)** wprowadź liczbę dni.
- Aby zastąpić horyzont czasowy ustalania, który jest zdefiniowany dla grupy zapotrzebowania i zapotrzebowania na towary dla określonego planu głównego, należy przejść do **Planowanie główne** \> **Ustawienia** \> **Plany główne** i wybrać plan główny. Następnie, na skróconej karcie w **Horyzont czasowy w dniach**, ustaw **Akceptacja** na wartość **Tak** wprowadź liczbę dni.

Jeśli funkcja automatycznego akceptowania jest włączona dla przebiegu planowania głównego, w którym jest używana Optymalizacja planowania, proces automatycznego akceptowania jest wykonywany zgodnie z konfiguracją automatycznego ustalania. Jeśli funkcja automatycznego akceptowania nie jest włączona lub jeśli planowanie jest uruchamiane na stronie **zapotrzebowanie netto**, proces automatycznego akceptowania zostanie pominięty.

## <a name="planning-optimization-vs-the-built-in-supply-chain-management-planning-engine"></a>Planowanie optymalizacji w porównaniu z wbudowanym aparatem planowania Supply Chain Management

Zarówno Optymalizacja planowania, jak i aparat planowania wbudowany w firmę Microsoft Dynamics 365 Supply Chain Management mogą być używane do automatycznego akceptowania zamówień planowanych. Istnieją jednak pewne ważne różnice. Na przykład w optymalizacji planowania jest używana Data zamówienia (to znaczy Data rozpoczęcia) w celu ustalenia, które zamówienia planowane mają zostać ustalone, wbudowany aparat planowania Supply Chain Management używa daty zapotrzebowania (Data zakończenia). Poniżej znajduje się podsumowanie różnic.

**Optymalizacja planowania**

- Automatyczne akceptowania jest oparte na dacie zamówienia (Data początkowa).
- Ponieważ Data zamówienia (Data początkowa) wyzwala akceptację, nie trzeba brać pod uwagę czasu realizacji w ramach horyzontu czasowego ustalania.
- Jeśli chcesz ustalić wszystkie zamówienia, które muszą się rozpoczynać w bieżącym tygodniu, horyzont czasowy ustalania musi wynosić jeden tydzień.

**Wbudowany silnik planowania Supply Chain Management**

- Automatyczne akceptowania jest oparte na dacie zapotrzebowania (Data końcowa).
- W celu zagwarantowania akceptacji zamówień w odpowiednim czasie horyzont czasowy ustalania musi być dłuższy niż czas realizacji.
- Jeśli chcesz ustalić wszystkie zamówienia, które muszą się rozpoczynać w bieżącym tygodniu, horyzont czasowy ustalania musi wynosić czas realizacji plus jeden tydzień.
