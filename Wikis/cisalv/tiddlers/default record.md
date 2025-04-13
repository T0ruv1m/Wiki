<<code "function CreateEmptyProdVersao: TProdVersao;
begin
  Result.FornecedorId := 0;
  Result.Valor_Unit := 0;
  Result.Estoque := 0;
  Result.Reserva := 0;
  Result.Status := '';
  Result.Att_em := 0;
end;" >>

instead use :

<<code " vEmpty := Default(TProdVersao);" >>