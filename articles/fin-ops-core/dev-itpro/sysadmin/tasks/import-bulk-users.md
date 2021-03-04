---
title: Importowanie użytkowników z usługi Azure Active Directory
description: Ta procedura umożliwia administratorom systemów ręczne importowanie wybranych użytkowników lub importowanie dużej liczby użytkowników z usługi Azure Active Directory.
author: peakerbl
manager: AnnBe
ms.date: 07/07/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 56b6666310309817ff30ccb3902721880b829ee0
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679821"
---
# <a name="import-users-from-azure-active-directory"></a>Importowanie użytkowników z usługi Azure Active Directory

[!include [banner](../../includes/banner.md)]

## <a name="import-select-users"></a>Importowanie wybranych użytkowników

Ta procedura umożliwia administratorom systemów importowanie wybranych użytkowników z usługi Azure Active Directory (Azure AD).

1. Użytkownicy zostaną zaimportowani z firmą w bieżącej sesji jako ich firmą domyślną. W razie potrzeby przed importowaniem użytkowników zmień bieżącą firmę.
2. Wybierz **Administrowanie systemem > Użytkownicy > Użytkownicy**.
3. Kliknij opcję **Importuj użytkowników**.
4. Zaznacz użytkowników, którzy mają zostać zaimportowani, i wybierz opcję **Importuj użytkowników**.

Po zakończeniu importu trzeba będzie przypisać role użytkownikom.

## <a name="import-users-in-bulk"></a>Zbiorowe importowanie użytkowników

Ta procedura umożliwia administratorom systemów importowanie dużej liczby użytkowników z usługi Azure Active Directory.
Zauważ, że w przypadku korzystania z opcji importu wsadowego nie można wybierać użytkowników.

## <a name="run-the-import-as-a-batch-job"></a>Wykonywanie importu jako zadania wsadowego
1. Użytkownicy zostaną zaimportowani z firmą w bieżącej sesji jako ich firmą domyślną. W razie potrzeby przed importowaniem użytkowników zmień bieżącą firmę.
2. Wybierz **Administrowanie systemem > Użytkownicy > Użytkownicy**.
3. Kliknij opcję **Import wsadowy**.
4. Rozwiń sekcję **Uruchom w tle**.
4. W polu **Przetwarzanie wsadowe** zaznacz opcję **Tak.
6. W polu **Grupa zadań wsadowych** wpisz lub wprowadź wartość. Ten krok jest opcjonalny.  
7. W polu **Prywatne** wybierz opcję **Tak**. Ten krok jest opcjonalny.  
8. W polu **Zadanie o znaczeniu krytycznym** wybierz opcję **Tak**. Ten krok jest opcjonalny.  
9. W polu **Monitorowanie kategorii wybierz opcję.
10. Kliknij przycisk **OK**.

Po zakończeniu importu trzeba będzie przypisać role użytkownikom.

## <a name="run-in-a-sandbox-environment"></a>Uruchamianie w środowisku piaskownicy
1. Wybierz opcję **Import wsadowy**.
2. Kliknij przycisk **OK**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]