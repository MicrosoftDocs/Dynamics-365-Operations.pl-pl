---
title: Tworzenie nowego układu magazynu
description: W tym temacie opisano sposób konfigurowania informacji na temat lokalizacji w magazynie.
author: perlynne
manager: tfehr
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventParameters, DefaultDashboard, InventLocation, WMSLocationWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 09666e95cc90913f1bf8555b9ff2c48aa55369ed
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435488"
---
# <a name="create-a-new-warehouse-layout"></a>Tworzenie nowego układu magazynu

[!include [banner](../../includes/banner.md)]

W tym temacie opisano sposób konfigurowania informacji na temat lokalizacji w magazynie. Dotyczy to tylko magazynów utworzonych przy użyciu funkcji „podstawowego magazynowania” dostępnych w module Zarządzanie zapasami, a nie magazynów utworzonych w module Zarządzanie magazynem. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.


## <a name="set-the-default-location-capacity"></a>Ustawianie domyślnej pojemności lokalizacji
1. Otwórz w okienku nawigacji **Moduły > Zarządzanie zapasami > Ustawienia > Parametry modułu Zarządzanie zapasami i magazynem**.
2. Wybierz kartę **Lokalizacje**.
3. W polu **Standardowa szerokość** wprowadź liczbę.
4. W polu **Standardowa długość** wprowadź liczbę.
5. W polu **Standardowa wysokość** wprowadź liczbę.
6. Wybierz opcję **Zapisz**.
7. Zamknij stronę.

## <a name="define-the-location-name-format"></a>Określanie formatu nazwy lokalizacji
1. Otwórz w okienku nawigacji **Moduły > Zarządzanie zapasami > Ustawienia > Podział magazynu > Magazyny**.
2. Wybierz pozycję **Nowy**.
3. W polu **Magazyn** wpisz wartość.
4. W polu **Nazwa** wpisz wartość.
5. W polu **Oddział** wybierz odpowiedni rekord z wyszukiwania.
6. Przełącz rozwinięcie sekcji **Nazwy lokalizacji**. Opcje w tej sekcji definiują domyślny format nazw lokalizacji. W naszym przykładzie uwzględnimy numery alei, regału i półki.  
7. W opcji **Uwzględnij korytarz** zaznacz wartość **Tak**.
8. W opcji **Uwzględnij regał** zaznacz wartość **Tak**. 
9. W polu **Format** dla regału wpisz wartość.
10. W opcji **Uwzględnij półkę** zaznacz wartość **Tak**.
11. W polu **Format** dla półki wpisz wartość.

## <a name="define-warehouse-locations"></a>Określanie lokalizacji w magazynach
1. W okienku akcji kliknij pozycję **Magazyn**.
2. Wybierz tę **Kreator lokalizacji**.
3. Wybierz pozycję **Następny**.
4. Usuń zaznaczenie opcji **Doki załadunkowe**.
5. Usuń zaznaczenie opcji **Lokalizacje zbiorcze**.
6. Wybierz **Następny**, aż zostanie wybrana opcja **Zakończ**.
7. Zamknij stronę.
8. Odśwież stronę.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]