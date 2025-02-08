
```
function TControleCliente.ValidarCPF(numCPF: string): boolean;

var
	cpf: string;
	x, total, dg1, dg2: Integer;
	ret: boolean;
begin
  ret := True;
  cpf := StringReplace(numCPF, '-', '', [rfReplaceAll]);
  cpf := StringReplace(cpf, '.', '', [rfReplaceAll]);
  if Trim(cpf) = '' then
    ret := False;
  for x := 1 to Length(numCPF) do
	  if not (numCPF[x] in ['0'..'9', '-', '.', ' ']) then
		  ret := False;
  if ret then
	begin
	  ret := True;
	  cpf := '';
	  for x := 1 to Length(numCPF) do
		  if numCPF[x] in ['0'..'9'] then
			  cpf := cpf + numCPF[x];
	  if Length(cpf) <> 11 then
		  ret := False;
	  if ret then
		begin
		  //1° dígito
		  total := 0;
		  for x := 1 to 9 do
			total := total + (StrToInt(cpf[x]) * x);
		  dg1 := total mod 11;
		  if dg1 = 10 then
			  dg1 := 0;
		  //2° dígito
		  total := 0;
		  for x := 1 to 8 do
			  total := total + (StrToInt(cpf[x + 1]) * (x));
		  total := total + (dg1 * 9);
		  dg2 := total mod 11;
		  if dg2 = 10 then
			  dg2 := 0;
		  //Validação final
      if (dg1 = StrToInt(cpf[10])) and (dg2 = StrToInt(cpf[11])) then
        ret := True
      else
        ret := False;
		  //Inválidos
      case AnsiIndexStr(cpf,['00000000000','11111111111','22222222222','33333333333','44444444444',
       '55555555555','66666666666','77777777777','88888888888','99999999999']) of
      	0..9: ret := False;
			end;
		end
	  else
    begin
		  //Se não informado deixa passar
		  if cpf = '' then
			  ret := True;
    end;
	end;
  result := ret;
end;
```