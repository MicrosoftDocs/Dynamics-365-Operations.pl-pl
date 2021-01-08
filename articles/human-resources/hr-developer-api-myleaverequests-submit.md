---
title: Przesyłanie wniosku o urlop do przepływu pracy
description: W rozwiązaniu Microsoft Dynamics 365 Human Resources można skorzystać z interfejsu API przesyłania MyLeaveRequests w celu przesłania wniosku urlopowego do przepływu pracy.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7552a4c921dc4a88034b5d2c87d5a9b47d699ae3
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4419998"
---
# <a name="submit-a-leave-request-to-workflow"></a>Przesyłanie wniosku o urlop do przepływu pracy

W rozwiązaniu Microsoft Dynamics 365 Human Resources można skorzystać z interfejsu API przesyłania MyLeaveRequests w celu przesłania wniosku urlopowego do przepływu pracy. Ten interfejs API jest udostępniany jako akcja w jednostce protokołu OData o nazwie MyLeaveRequests.

## <a name="prerequisites"></a>Wymagania wstępne

Wniosek urlopowy musi zostać zapisany w bazie danych i być możliwy do pobrania za pośrednictwem jednostki MyLeaveRequests.

## <a name="permissions"></a>Uprawnienia

Do wywołania tego interfejsu API jest wymagane jedno z poniższych uprawnień. Aby uzyskać więcej informacji na temat uprawnień i ich wybierania, zobacz [Uwierzytelnianie](hr-developer-api-authentication.md).

| Typ uprawnienia                    | Uprawnienia (od najmniej uprzywilejowanych do najbardziej uprzywilejowanych) |
|------------------------------------|--------------------------------------------------------|
| Delegowane (konto służbowe lub uczelniane) | user\_impersonation                                    |

## <a name="https-request"></a>Żądanie HTTPS

<!-- { "blockType": "ignored" } -->
```HTTP
POST https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/MyLeaveRequests(RequestId='{requestId}', LeaveType='{leaveType}', LeaveDate={leaveDate}, dataAreaId={dataArea})/Microsoft.Dynamics.DataEntities.submit?cross-company=true
```

Żądanie jest zgodne ze standardami protokołu OData. Parametry {requestId}, {leaveType}, {leaveDate} i {dataArea} odwołują się do pól tworzących zbiorczy klucz naturalny jednostki MyLeaveRequests.

> [!NOTE]
> Pola jednostki MyLeaveRequests odwołują się do pojedynczego wiersza we wniosku urlopowym, ale wywołanie interfejsu API przesyłania spowoduje przesłanie całego wniosku urlopowego (wszystkich wierszy) do przepływu pracy.

### <a name="request-headers"></a>Nagłówki żądań

| Nagłówek         | Value                     |
|----------------|---------------------------|
| Autoryzacja  | Okaziciel {token} (wymagana) |
| Typ zawartości   | application/json          |

### <a name="request-body"></a>Treść wniosku

W tej metodzie nie należy podawać treści wniosku.

### <a name="response"></a>Odpowiedź

Pomyślna odpowiedź zawsze ma treść **204 Brak zawartości**.

Nieautoryzowane obiekty wywołujące otrzymają odpowiedź **401 Nieautoryzowany** lub **403 Zabroniony**.

Jeśli przesyłanie się nie powiedzie (na przykład z powodu nieudanej weryfikacji), odpowiedzią będzie **500 Błąd serwera**, a treść odpowiedzi będzie zawierała obiekt JSON z dalszymi szczegółami.

## <a name="example"></a>Przykład

```http
POST https://aos-rts-sf-550e5c091f6-prod-westus2.hr.talent.dynamics.com/namespaces/b2eb8003-334f-4a84-ab63-edbe23569090/data/MyLeaveRequests(RequestId='USMF-000065', LeaveType='Vacation', LeaveDate=2019-10-04T12:00:00Z, dataAreaId='USMF')/Microsoft.Dynamics.DataEntities.submit
```

```json
{
  "error": {
    "code": "",
    "message": "An error has occurred.",
    "innererror": {
      "message": "Exception occurred while executing action submit on Entity MyLeaveRequest: The request would put the 'Vacation' balance below the allowed minimum balance on 9/10/2019.",
      "type": "System.InvalidOperationException",
      "stacktrace": "   at Microsoft.Dynamics.Platform.Integration.Services.OData.Action.ActionInvokable.Invoke()   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateProcessor.ActionInvocation(ChangeOperationContext context, ActionInvokable action)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateManager.<>c__DisplayClass13_0.<ScheduleInvokable>b__0(ChangeOperationContext context)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.ChangeInfo.ExecuteActionsInCompanyContext(IEnumerable`1 actionList, ChangeOperationContext operationContext)\r\n   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.ChangeInfo.ExecuteActions(ChangeOperationContext context)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateManager.SaveChanges()   at Microsoft.Dynamics.Platform.Integration.Services.OData.AxODataDelegatingHandler.<SaveChangesAsync>d__3.MoveNext()"
    }
  }
}
```

## <a name="validation-and-error-messages"></a>Weryfikacja i komunikaty o błędach

W ramach wywołania interfejsu API przesyłania moduł Human Resources przeprowadza weryfikację logiki biznesowej przed rozpoczęciem przesyłania, co gwarantuje, że wniosek urlopowy będzie w prawidłowym stanie do przesłania. W razie niepowodzenia sprawdzania poprawności mogą się w odpowiedzi pojawić następujące komunikaty o błędach:

 - Zaakceptowanie wniosku spowodowałaby zmniejszenie salda „{LeaveTypeId}” do poziomu niższego niż dozwolone saldo minimalne na dzień {date}.
 - Nie można przesłać wniosku urlopowego w stanie Ukończone.
 - Nie można przesłać lub zapisać wniosku, ponieważ nie wprowadzono żadnych zmian. Dodaj lub zaktualizuj ilość albo typ urlopu, a następnie spróbuj ponownie.
 - Wprowadzony wniosek urlopowy zawiera co najmniej jeden dzień z taką samą datą i typem urlopu, co istniejący oczekujący wniosek. Aby wprowadzić zmiany, wycofaj istniejący wniosek.
 - Kod przyczyny „{ReasonCodeId}” nie ma zastosowania do żadnego typu urlopu we wniosku.
 - Typ urlopu „{LeaveTypeId}” wymaga kodu przyczyny. Wybierz odpowiedni typ i kod przyczyny.
 - Wniosek urlopowy nie został pomyślnie przesłany. Wniosek urlopowy został zapisany jako wersja robocza wniosku.

## <a name="see-also"></a>Informacje dodatkowe

- [MyLeaveRequests — omówienie](hr-developer-api-myleaverequests-overview.md)
- [Uwierzytelnianie](hr-developer-api-authentication.md)