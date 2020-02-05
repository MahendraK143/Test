Class<?> clazz = Class.forName(String.format("com.daimler.operations.%s", msg.getType()));
			Constructor<?> mc = clazz.getConstructor();
			Object obj = mc.newInstance();

			Operation op = (Operation) obj;
			op.init(table, query, parent);

			System.out.println("ProcessorImpl Invoking Service Operation");
			op.process(params.get(C.Id), params.get(C.Vins));
