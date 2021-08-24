---
title: Tworzenie schematów naliczania
description: W tym temacie opisano sposób tworzenia schematu naliczania.
author: aprilolson
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerAccrualTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8ab36250365fefe37329f87769f16f546ca7326654db42aa7acb61fb37604ce2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6779520"
---
# <a name="create-accrual-schemes"></a>Tworzenie schematów naliczania

[!include [banner](../../includes/banner.md)]

W tym temacie opisano sposób tworzenia schematu naliczania. W zadaniu wykorzystano firmę demonstracyjną USMF.

1. Otwórz **Okienko nawigacji > Moduły > Księga główna > Konfiguracja arkusza > Schematy naliczania**.
2. Wybierz pozycję **Nowy**.
3. W polu **Identyfikacja naliczania** wpisz wartość.
4. W polu **Opis schematu naliczania** wpisz wartość.
5. W polu **Debet** podaj żądane wartości. Zdefiniowane konto główne zastąpi konto główne strony debetowej w wierszu załącznika arkusza oraz będzie również służyć do wycofywania odroczenia opartego na transakcjach naliczeń finansowych.  
6. W polu **Kredyt** podaj żądane wartości. Zdefiniowane konto główne zastąpi konto główne strony kredytowej w wierszu załącznika arkusza oraz będzie również służyć do wycofywania odroczenia opartego na transakcjach naliczeń finansowych.  
7. W polu **Załącznik** wybierz sposób dobierania załącznika podczas księgowania transakcji.
8. W polu **Opis** wpisz wartość opisującą transakcje, które będą księgowane.
9. W polu **Częstotliwość okresu** wybierz, jak często mają mieć miejsce transakcje.
10. W polu **Liczba wystąpień według okresu** wprowadź liczbę.
11. W polu **Księguj transakcje** wybierz, kiedy transakcje mają być księgowane, np. **Miesięcznie**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]